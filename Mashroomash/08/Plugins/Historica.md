Tip

Historica have new document system at [historica](https://historica.pages.dev/)
(Not) Smart and dynamic extraction point of time in your note or multi notes

---

- _(Not) Smart and dynamic extraction_ point of time in your note or multi notes
- _Auto sort_ and _visualize_ the time in your note
- Support for two styles of visualization
- _(Not) Smart generates the summary_ of content related to the point of time in your note
- Multi files support
- Export your timeline as image/pdf or copy it to clipboard

---

What! Another **GPT** tools again 😢

No 😍, it is not

---

###### Simplest use case

Simply create a historica code block somewhere in your file

```markdown
 ```historica

 ```
```

No need any configuration to make it work

---

Oh, you want more configuration?

---

###### Includes multi files

````toml
```historica

style=1 
 
include_files=["file1.md", "sub_dir/file2.md", "sub_dir2/sub_dir3/file3.md] 

```
````

Style maybe 1 or 2

Directories in include_files are relative paths to vault directory

Tip

You can use "all" (without an array notation) to include all files in vault, this option is not encouraged because, it  
is a heavy task, and Historica not good at detecting non-English string

---

###### Pin special point of time as "now"

Historica smart enough to work with all related time phrases like "now," "2 days ago", But it is also mean those related point of time always be parsed from current time from your system. So now you can pin a point of time as "now," also using natural language too.

````toml
```historica
pin_time="1997/Jun/12"
```
````

![](https://raw.githubusercontent.com/nhannht/obsidian-historica/HEAD/images/.README_images/historica_pin_time_example.png)

Historica can even parse timezone too, just input pin_time like this "1997/Jun/12 GTM+7"?

---

###### Query your time strictly

Give a stricter query by specific multi time ranges

````toml

```historica
[query.from-1997-to-2022]  
start="1997/Jun/12"  
end="2022/Jun/13"  
  
[query.from-1000-to-1500]  
start="1000/Jun/12"  
end="1500/Jun/13"

```

````

![](https://raw.githubusercontent.com/nhannht/obsidian-historica/HEAD/images/.README_images/historica_query_example.png)

Tip

Historica using `toml` as configuration syntax, so a table/table array is the syntax to define your query. You can  
check more of them [here](https://toml.io/en/v1.0.0#table)

---

###### Export or copy the timeline

Just right-click anywhere in the timeline. The helper menu will appear.

![](https://raw.githubusercontent.com/nhannht/obsidian-historica/HEAD/images/.README_images/historica_helper_menu.png)

Note

This feature was being disabled on mobile due to unreliable behaviour

---

###### Smart theme

Historica has it own theme—Legend Larva, which I had carefully (I just joked, haha) designed, but now you have the option to use the semantic theme, which will change based on your current Obsidian Theme

````toml
```historica
smart_theme=true
```
````

Or using global setting option

---

###### Implicit or explicit showing point of time

Control how time entry will be display in your timeline

````toml
```historica
implicit_time=true/false
```
````

---

Style 1

![](https://raw.githubusercontent.com/nhannht/obsidian-historica/HEAD/images/.README_images/ebfc0193.png)

---

Style 2

![](https://raw.githubusercontent.com/nhannht/obsidian-historica/HEAD/images/.README_images/d9a7b9af.png)

It is not smart like it seems. Just like me