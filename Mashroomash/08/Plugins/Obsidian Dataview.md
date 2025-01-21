calendar file.mtime
where weight > 1
where !completed
Sort date desc
> [!example] Context
> - [Dataview](#Dataview)
> 	- [Examples](#Examples)
> 	- [Usage](#Usage)
> 		- [**Data**](#**Data**)
> 		- [**Querying**](#**Querying**)
> 		- [JavaScript Queries: Security Note](#JavaScript%20Queries:%20Security%20Note)
> 	- [Contributing](#Contributing)
> 		- [Local Development](#Local%20Development)
> 		- [Installing to Other Vaults](#Installing%20to%20Other%20Vaults)
> 		- [Building Documentation](#Building%20Documentation)
> 		- [Using Dataview Types In Your Own Plugin](#Using%20Dataview%20Types%20In%20Your%20Own%20Plugin)
> 	- [Support](#Support)
# Dataview
Treat your [Obsidian Vault](https://obsidian.md/) as a database which you can query from. Provides a JavaScript API and  
pipeline-based query language for filtering, sorting, and extracting data from Markdown pages. See the Examples section  
below for some quick examples, or the full [reference](https://blacksmithgu.github.io/obsidian-dataview/) for all the details.

## Examples

Show all games in the game folder, sorted by rating, with some metadata:

````markdown
| File | time-played | length | rating |
| ---- | ----------- | ------ | ------ |

````

![Game Example](https://raw.githubusercontent.com/blacksmithgu/obsidian-dataview/HEAD/docs/docs/assets/game.png)

---

List games which are MOBAs or CRPGs.

````markdown

````

![Game List](https://raw.githubusercontent.com/blacksmithgu/obsidian-dataview/HEAD/docs/docs/assets/game-list.png)

---

List all markdown [tasks](https://blacksmithgu.github.io/obsidian-dataview/data-annotation/#tasks) in un-completed projects:

````markdown

````

![Task List](https://raw.githubusercontent.com/blacksmithgu/obsidian-dataview/HEAD/docs/docs/assets/project-task.png)

---

Show all files in the `books` folder that you read in 2021, grouped by genre and sorted by rating:

````markdown

````

![Books By Genre](https://raw.githubusercontent.com/blacksmithgu/obsidian-dataview/HEAD/docs/docs/assets/books-by-genre.png)

## Usage

For a full description of all features, instructions, and examples, see the [reference](https://blacksmithgu.github.io/obsidian-dataview/). For a more brief outline, let us examine the two major aspects of Dataview: _data_ and _querying_.

#### **Data**

Dataview generates _data_ from your vault by pulling  
information from **Markdown frontmatter** and **Inline fields**.

- Markdown frontmatter is arbitrary YAML enclosed by `---` at the top of a markdown document which can store metadata  
    about that document.
- Inline fields are a Dataview feature which allow you to write metadata directly inline in your markdown document via  
    `Key:: Value` syntax.

Examples of both are shown below:

```yaml
---
alias: "document"
last-reviewed: 2021-08-17
thoughts:
  rating: 8
  reviewable: false
---
```

```markdown
# Markdown Page

Basic Field:: Value
**Bold Field**:: Nice!
You can also write [field:: inline fields]; multiple [field2:: on the same line].
If you want to hide the (field3:: key), you can do that too.
```

#### **Querying**

Once you've annotated documents and the like with metadata, you can then query it using any of Dataview's four query  
modes:

1. **Dataview Query Language (DQL)**: A pipeline-based, vaguely SQL-looking expression language which can support basic  
    use cases. See the [documentation](https://blacksmithgu.github.io/obsidian-dataview/query/queries/) for details.
    
    ````markdown
    | File | File | Rating |
| ---- | ---- | ------ |

    ````
    
2. **Inline Expressions**: DQL expressions which you can embed directly inside markdown and which will be evaluated in  
    preview mode. See the [documentation](https://blacksmithgu.github.io/obsidian-dataview/reference/expressions/) for  
    allowable queries.
    
    ```markdown
    We are on page Obsidian Dataview.
    ```
    
3. **DataviewJS**: A high-powered JavaScript API which gives full access to the Dataview index and some convenient  
    rendering utilities. Highly recommended if you know JavaScript, since this is far more powerful than the query  
    language. Check the [documentation](https://blacksmithgu.github.io/obsidian-dataview/api/intro/) for more details.
    
    ````markdown
    <div><h4><span></span><span class="dataview small-text">1</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">1</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task="-" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">1</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task="-" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">8</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">6</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="-" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span><ul class="contains-task-list"><li data-task="-" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="-" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></li></ul></div><h4><span></span><span class="dataview small-text">22</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="r" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="n" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="n" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="r" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="r" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">8</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="n" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">8</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="n" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="o" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="r" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">7</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">25</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">5</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></li></ul></div><h4><span></span><span class="dataview small-text">26</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span><ul class="contains-task-list"><li data-task="x" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="x" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="x" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="x" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="x" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">3</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">8</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div><h4><span></span><span class="dataview small-text">69</span></h4><div class="dataview result-group"><ul class="contains-task-list"><li data-task=" " class="dataview task-list-item"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="-" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="r" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="l" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="n" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="o" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="k" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="U" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=")" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=":" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="(" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="}" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="=" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="{" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="?" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="*" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="!" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task=">" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="<" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="/" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="+" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="_" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="%" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="&amp;" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="." class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="@" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="#" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="'" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="a" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="A" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="b" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="B" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="c" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="C" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="d" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="D" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="e" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="E" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="f" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="F" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="g" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="G" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="h" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="H" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="i" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="I" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="m" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="M" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="p" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="P" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="s" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="S" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="u" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="v" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="w" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="W" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="z" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="Z" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="0" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="1" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="2" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="3" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="4" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="5" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="6" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="7" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="8" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="9" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li><li data-task="§" class="dataview task-list-item is-checked"><input type="checkbox" class="dataview task-list-item-checkbox"><span></span></li></ul></div></div>
    ````
    
4. **Inline JS Expressions**: The JavaScript equivalent to inline expressions, which allow you to execute arbitrary JS  
    inline:
    
    ```markdown
    This page was last modified at 24.06.25 03:06.
    ```
    

#### JavaScript Queries: Security Note

JavaScript queries are very powerful, but they run at the same level of access as any other Obsidian plugin. This means  
they can potentially rewrite, create, or delete files, as well as make network calls. You should generally write  
JavaScript queries yourself or use scripts that you understand or that come from reputable sources. Regular Dataview  
queries are sandboxed and cannot make negative changes to your vault (in exchange for being much more limited).

## Contributing

Contributions via bug reports, bug fixes, documentation, and general improvements are always welcome. For more major  
feature work, make an issue about the feature idea / reach out to me so we can judge feasibility and how best to  
implement it.

#### Local Development

The codebase is written in TypeScript and uses `rollup` / `node` for compilation; for a first time set up, all you  
should need to do is pull, install, and build:

```console
foo@bar:~$ git clone git@github.com:blacksmithgu/obsidian-dataview.git
foo@bar:~$ cd obsidian-dataview
foo@bar:~/obsidian-dataview$ npm install
foo@bar:~/obsidian-dataview$ npm run dev
```

This will install libraries, build dataview, and deploy it to `test-vault`, which you can then open in Obsidian. This  
will also put `rollup` in watch mode, so any changes to the code will be re-compiled and the test vault will automatically  
reload itself.

#### Installing to Other Vaults

If you want to dogfood dataview in your real vault, you can build and install manually. Dataview is predominantly a  
read-only store, so this should be safe, but watch out if you are adjusting functionality that performs file edits!

```console
foo@bar:~/obsidian-dataview$ npm run build
foo@bar:~/obsidian-dataview$ ./scripts/install-built path/to/your/vault
```

#### Building Documentation

We use `MkDocs` for documentation (found in `docs/`). You'll need to have python and pip to run it locally:

```console
foo@bar:~/obsidian-dataview$ pip3 install mkdocs mkdocs-material mkdocs-redirects
foo@bar:~/obsidian-dataview$ cd docs
foo@bar:~/obsidian-dataview/docs$ mkdocs serve
```

This will start a local web server rendering the documentation in `docs/docs`, which will live-reload on change.  
Documentation changes are automatically pushed to `blacksmithgu.github.io/obsidian-dataview` once they are merged  
to the main branch.

#### Using Dataview Types In Your Own Plugin

Dataview publishes TypeScript typings for all of its APIs onto NPM (as `blacksmithgu/obsidian-dataview`). For  
instructions on how to set up development using Dataview, see [setup instructions](https://blacksmithgu.github.io/obsidian-dataview/plugin/develop-against-dataview/).

## Support

Have you found the Dataview plugin helpful, and want to support it? I accept donations which go towards future  
development efforts. I generally do not accept payment for bug bounties/feature requests, as financial incentives add  
stress/expectations which I want to avoid for a hobby project!