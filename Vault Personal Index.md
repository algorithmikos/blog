```dataviewjs
dv.table(["Title", "ID"], 
    dv.pages('"blog"')
    .sort(p => -p.file.ctime.ts)
    .map(p => {
        // Create button element
        let btn = document.createElement("button");
        btn.textContent = `📋 ${p.id}`;
        btn.style.cursor = "pointer";
        
        // Set click event to copy the ID
        btn.onclick = () => {
            navigator.clipboard.writeText(p.id);
        };
		console.log(p.file)

        return [`[${p.title}](${p.file.path})`, btn];
    })
);

```
