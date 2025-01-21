---
URL: https://ayon.ynput.io/docs/admin_server_deployment
thumbnail: 
site: "[[]]"
date: 2024-10-08T13:21:11
duration: 1
topics: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[../01 Maps/Themes/Article|Article]] 
# Server deployment | AYON Docs

Description:: ## Requirements[​](https://ayon.ynput.io/docs/admin_server_deployment#requirements "Direct link to Requirements")

-   Docker with the compose plugin. To install the latest Docker, you can use this script: [https://get.docker.com](https://get.docker.com/)
-   GNU Make (on Linux and MacOS)
-   If you use a stand-alone  script instead of the compose plugin, make sure to use  wherever \- is used in this tutorial.
-   For production, using Linux is highly recommended. However, for evaluation purposes, Windows with WSL (Windows Subsystem for Linux) can be used.

## Installation[​](https://ayon.ynput.io/docs/admin_server_deployment#installation "Direct link to Installation")

-   Windows
-   Linux
-   Mac

1.  Clone [ayon-docker repository](https://github.com/ynput/ayon-docker) to your local machine.
2.  Tweak the  file according to your requirements.
3.  You may use the `.env` file to set environment variables.
4.  Manually install addons to the `addons` directory or automatically install later on (recommended).
5.  Modify the default settings in the `settings/template.json` file (see [provisioning page](https://ayon.ynput.io/docs/admin_server_provisioning/#configuration-file)).
6.  Run the stack using \-
7.  Run `make setup`
8.  Once the setup is complete, navigate to [http://localhost:5000/](http://localhost:5000/)
9.  If you haven't used `template.json` file to create a user, you will be prompted to create one now.

## Updates[​](https://ayon.ynput.io/docs/admin_server_deployment#updates "Direct link to Updates")

If you are using our official docker images and docker compose for AYON server deployment, updating is as easy as

```
docker pull ynput/ayon:latest #replace with corresponding image version if you don't want latestdocker compose up -d --build
```


# Server configuration

This documentation provides detailed information about each configuration option available for the Ayon server. Configuration parameters can be set through environment variables, prefixed with `AYON_`.

### HTTP Server Settings[​](https://ayon.ynput.io/docs/admin_server_configuration#http-server-settings "Direct link to HTTP Server Settings")

- **HTTP Listen Address**
    
    - Environment Variable: `AYON_HTTP_LISTEN_ADDRESS`
    - Default: `0.0.0.0`
    - Description: An address the API server listens on.
- **HTTP Listen Port**
    
    - Environment Variable: `AYON_HTTP_LISTEN_PORT`
    - Default: `5000`
    - Description: A port the API server listens on.

### Directory Paths[​](https://ayon.ynput.io/docs/admin_server_configuration#directory-paths "Direct link to Directory Paths")

- **API Modules Directory**
    
    - Environment Variable: `AYON_API_MODULES_DIR`
    - Default: `api`
    - Description: Path to the directory containing the API modules.
- **Addons Directory**
    
    - Environment Variable: `AYON_ADDONS_DIR`
    - Default: `/addons`
    - Description: Absolute path to the directory containing the addons.
- **Frontend Directory**
    
    - Environment Variable: `AYON_FRONTEND_DIR`
    - Default: `/frontend`
    - Description: Path to the directory containing the frontend files.

### Authentication Settings[​](https://ayon.ynput.io/docs/admin_server_configuration#authentication-settings "Direct link to Authentication Settings")

- **Authentication Password Pepper**
    
    - Environment Variable: `AYON_AUTH_PASS_PEPPER`
    - Default: `supersecretpasswordpepper`
    - Description: A secret string used to salt the password hash.
- **Minimum Password Length**
    
    - Environment Variable: `AYON_AUTH_PASS_MIN_LENGTH`
    - Default: `8`
    - Description: Minimum password length.
- **Password Complexity Requirement**
    
    - Environment Variable: `AYON_AUTH_PASS_COMPLEX`
    - Default: `True`
    - Description: Enforce using a complex password.

### Database and Session Management[​](https://ayon.ynput.io/docs/admin_server_configuration#database-and-session-management "Direct link to Database and Session Management")

- **Redis URL**
    
    - Environment Variable: `AYON_REDIS_URL`
    - Default: `redis://redis/`
    - Description: Connection string for Redis.
    - Example: `redis://user:password123@redis.example.com:6379`
- **Redis Channel**
    
    - Environment Variable: `AYON_REDIS_CHANNEL`
    - Default: `pype:c`
    - Description: Redis channel name for system messages.
- **Postgres URL**
    
    - Environment Variable: `AYON_POSTGRES_URL`
    - Default: `postgres://ayon:ayon@postgres/ayon`
    - Description: Connection string for Postgres.
    - Example: `postgres://user:password123@postgres.example.com:5432/ayon`
- **Session TTL**
    
    - Environment Variable: `AYON_SESSION_TTL`
    - Default: `86400` (24 hours)
    - Description: Session lifetime in seconds.

### Security and Logging[​](https://ayon.ynput.io/docs/admin_server_configuration#security-and-logging "Direct link to Security and Logging")

- **Max Failed Login Attempts**
    
    - Environment Variable: `AYON_MAX_FAILED_LOGIN_ATTEMPTS`
    - Default: `10`
    - Description: Maximum number of failed login attempts.
- **Failed Login Ban Time**
    
    - Environment Variable: `AYON_FAILED_LOGIN_BAN_TIME`
    - Default: `600`
    - Description: Interval in seconds to ban IP addresses with too many failed login attempts.
- **Message of the Day (MOTD)**
    
    - Environment Variable: `AYON_MOTD`
    - Default: `None`
    - Description: Message of the day.
    - Example: `Welcome to Ayon!`
- **MOTD Path**
    
    - Environment Variable: `AYON_MOTD_PATH`
    - Default: `/storage/motd.md`
    - Description: Path to the MOTD file.

# Installing addons

## Directory structure[​](https://ayon.ynput.io/docs/admin_server_installing_addons#directory-structure "Direct link to Directory structure")

Ayon addons are installed into the `addons` directory, following the structure:

```
addons/  └── {addon_name}/      └── {addon_version}/
```

Each version of an addon contains the following components:

- Addon base class (`__init__.py`): This is the main class that defines the addon's functionality.
- Server code (optional): This includes any server-side code for the addon.
- Frontend code (optional): This contains the frontend code for the addon, if applicable.
- Binary package for the client application (optional): This is a pre-compiled binary package that can be used by the client application.

For example, an addon named `example` with version `1.0.0` would have the following directory structure:

```
addons/  └── example/      └── 1_0_0/          ├── __init__.py          ├── frontend/ (optional - frontend code)          ├── private/ (optional - static files available to logged in users)          └── public/ (optional - publicly available static files, such as icons)
```

This structure allows for multiple versions of addons to coexist, and makes it easy to manage and update addons in your Ayon server.

## Using Development Versions of Addons[​](https://ayon.ynput.io/docs/admin_server_installing_addons#using-development-versions-of-addons "Direct link to Using Development Versions of Addons")

The common practice for working with development versions of addons is to use the  directory instead of a specific version number. This allows you to separate the development version from production versions and makes it easier to test and debug your addons.

To set up a development version of an addon, follow these steps:

1. Create a directory for the addon within the `addons` folder using the addon's name.

```
mkdir addons/example
```

2. Navigate to the newly created addon directory.

```
cd addons/example
```

3. Clone the addon repository into the  directory.

```
git clone https://github.com/ynput/ayon-example-addon dev
```

Your addon's directory structure should now look like this:

```
addons/  └── example/      └── dev/          ├── __init__.py          └── ...
```

# Provisioning

## Configuration file[​](https://ayon.ynput.io/docs/admin_server_provisioning#configuration-file "Direct link to Configuration file")

Ayon server offers a convenient method for bootstrapping its basic settings using a single JSON file. This enables you to quickly set up the server with your desired configurations.

Security Considerations

Using the bootstrapped settings is particularly useful during the testing phase of your Ayon server. However, once the server is properly set up and configured, it is strongly recommended to remove the `settings/template.json` file.

The reason for this recommendation is that the `template.json` file may contain sensitive information, such as secrets and passwords, in plain text. Storing these credentials in an unsecured manner poses a security risk, as unauthorized users may gain access to the server's sensitive data.

## File structure[​](https://ayon.ynput.io/docs/admin_server_provisioning#file-structure "Direct link to File structure")

By default, the server expects the configuration file to be located at `settings/template.json`. The settings within this file will be applied each time you run the `make setup` command.

```
settings/  └── template.json
```

The `template.json` file contains a dictionary with several optional keys that allow you to customize various aspects of your Ayon server. The available keys are:

- `secrets`
- `users`
- `accessGroups`

### Secrets[​](https://ayon.ynput.io/docs/admin_server_provisioning#secrets "Direct link to Secrets")

The `secrets` key is used for storing sensitive information that the server and addons have access to. Since settings are sent to clients, secrets provide a way to hide sensitive data from users. Both the server part of addons and services have access to secrets and may use them as needed.

Example:

```
"secrets": {  "secret_api_key": "123456789abcd"}
```

In this example, a `secret_api_key` is stored within the `secrets` key. This secret can be accessed by the server and addons, but will not be exposed to the users.

## Access groups[​](https://ayon.ynput.io/docs/admin_server_provisioning#access-groups "Direct link to Access groups")

User access groups define the level of access and permissions a user has within a project. Each role allows whitelisting certain rights to perform specific actions, such as reading, creating, updating, and deleting project resources.

If not provided, default access groups "artist", "viewer" and "editor" are created.

### Role definition example[​](https://ayon.ynput.io/docs/admin_server_provisioning#role-definition-example "Direct link to Role definition example")

The following example demonstrates how to create a single role named "artist". This role grants users the ability to read and update subfolders, but only if the user has tasks assigned on a parent folder.

```
"accessGroups" : [  {    "name": "artist",    "data": {      "read": {        "enabled": true,        "access_list": [{ "type": "assigned"}]      },      "create": {        "enabled": true,        "access_list": []      },      "delete": {        "enabled": true,        "access_list": []      },      "update": {        "enabled": true,        "access_list": [{ "type": "assigned"}]      }    }  }]
```

For more information on the role data structure, please refer to the API documentation.

### Users[​](https://ayon.ynput.io/docs/admin_server_provisioning#users "Direct link to Users")

The `users` key is used to define user accounts for the Ayon server. The value of this key is an array of dictionaries, with each dictionary representing a user account.

If the `users` key is not provided in the `template.json` file, a default administrator with the username `admin` and password `admin` will be created.

```
"users": [  {    "name": "admin",    "password": "admin",    "fullName": "Ayon admin",    "isAdmin": true,    "forceUpdate": true  }]
```

#### `forceUpdate` (boolean)[​](https://ayon.ynput.io/docs/admin_server_provisioning#forceupdate-boolean "Direct link to forceupdate-boolean")

Ensures that the setup command will always update the existing user with the information from the `template.json` file, including the password.

#### `fullName` (string)[​](https://ayon.ynput.io/docs/admin_server_provisioning#fullname-string "Direct link to fullname-string")

Represents the full name of the user.

#### `email` (string)[​](https://ayon.ynput.io/docs/admin_server_provisioning#email-string "Direct link to email-string")

Represents the user's email address, which is used for authentication and communication purposes.

#### `avatarUrl` (string)[​](https://ayon.ynput.io/docs/admin_server_provisioning#avatarurl-string "Direct link to avatarurl-string")

Contains the URL of the user's avatar image.

#### `isManager` (boolean)[​](https://ayon.ynput.io/docs/admin_server_provisioning#ismanager-boolean "Direct link to ismanager-boolean")

Indicates if the user is a manager. A manager has elevated privileges within the server.

#### `isAdmin` (boolean)[​](https://ayon.ynput.io/docs/admin_server_provisioning#isadmin-boolean "Direct link to isadmin-boolean")

Indicates if the user is an administrator. An administrator has the highest level of access and control within the server.

#### `isService` (boolean)[​](https://ayon.ynput.io/docs/admin_server_provisioning#isservice-boolean "Direct link to isservice-boolean")

Indicates if the user is a service account. A service account should be only used by addon services and it should be authenticated using an API key.

#### `isGuest` (boolean)[​](https://ayon.ynput.io/docs/admin_server_provisioning#isguest-boolean "Direct link to isguest-boolean")

Indicates if the user is a guest.

#### `password` (string)[​](https://ayon.ynput.io/docs/admin_server_provisioning#password-string "Direct link to password-string")

Represents the user's password. This field is required for authentication purposes.

#### `apiKey` (string)[​](https://ayon.ynput.io/docs/admin_server_provisioning#apikey-string "Direct link to apikey-string")

Contains the API key associated with service users. This key is used when a service interacting with the server through the API.

####  (array of strings)[​](https://ayon.ynput.io/docs/admin_server_provisioning#defaultaccessgroups-array-of-strings "Direct link to defaultaccessgroups-array-of-strings")

Lists the access groups assigned to the user on new projects. These access groups determine the user's privileges and access levels within a project.

Example:

```
"defaultAccessGroups": ["artist"]
```

#### `accessGroups`[​](https://ayon.ynput.io/docs/admin_server_provisioning#accessgroups "Direct link to accessgroups")

Lists the access groups assigned to the user on particular projects.

Example:

```
"accessGroups": {  "example_project1": ["artist"],  "example_project2": ["artist", "viewer"]}
```

# Ayon services

Ayon services are independent processes provided by addons that run in Docker containers outside of the main Ayon stack. These services connect to the server using the HTTP API and perform various tasks in the background. Since they are not directly connected to the database but use the API, it is safe to run services even on different premises. This can be beneficial, for example, when the Ayon server is running in a public cloud while several services run on-premises.

## Service account[​](https://ayon.ynput.io/docs/admin_server_services#service-account "Direct link to Service account")

Ensure you have a service account with API key. You can create a service account using either the provisioning file (`settings/template.json`) or the web interface.

template.json

```
  {      "name": "service",      "apiKey": "veryinsecureapikey",      "isService": true  }
```

## ASH[​](https://ayon.ynput.io/docs/admin_server_services#ash "Direct link to ASH")

To run a managed service (controllable from the web interface), the worker machine needs to run the Ayon Service Host (ASH). ASH is a small process that handles spawning services as specified by the administrator in the services page. It periodically checks the services declared in the Ayon server database and starts them if they are not running. It also provides a simple API for services to report their status and to receive configuration.

### Setting up using docker compose[​](https://ayon.ynput.io/docs/admin_server_services#setting-up-using-docker-compose "Direct link to Setting up using docker compose")

To add ASH as a service to your  file, you can either use the same stack as the server or create a completely separate one.

You need to provide the `AYON_API_KEY` and `AYON_SERVER_URL` environment variables. Additionally, ASH requires the  file to be mounted as a volume to control the Docker process and spawn services.

```
worker:                                                                                                                             image: ynput/ayon-ash:latest  hostname: worker01  restart: unless-stopped  volumes:    - "/var/run/docker.sock:/var/run/docker.sock"  environment:    - "AYON_API_KEY=veryinsecureapikey"    - "AYON_SERVER_URL=https://ayon.example.com"
```

## Troubleshooting[​](https://ayon.ynput.io/docs/admin_server_services#troubleshooting "Direct link to Troubleshooting")

### Handling Failed Services[​](https://ayon.ynput.io/docs/admin_server_services#handling-failed-services "Direct link to Handling Failed Services")

In case a service fails to stop and remove its container, you may need to manually intervene to stop the orphaned containers.

Ayon service containers are easily identifiable by their naming convention. They use the service name with an `aysvc_` prefix. This prefix allows you to quickly filter and manage Ayon service containers when working with Docker commands.

Run the following command to list all running Docker containers and filter the results to display only Ayon service containers.

```
$ docker ps | grep aysvcaf60516ccb4b   ynput/ayon-openpype-import:latest   "python -m processor"    2 weeks ago    Up 2 weeks   aysvc_op3import
```

Once you've identified the orphaned service containers, use the \- command to stop them individually. Replace `<container_id>` with the actual container ID of the orphaned container:

```
docker stop <container_id>
```

Since the containers are started with the `--remove` flag, they will be automatically removed once they are stopped.