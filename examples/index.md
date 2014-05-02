# 演示文档

---

````html
<style>
<style>
#demos section {
    overflow: hidden;
}
.sortable {
    width: 310px;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}
.sortable.grid {
    overflow: hidden;
}
.sortable li {
    list-style: none;
    border: 1px solid #CCC;
    background: #F6F6F6;
    color: #1C94C4;
    margin: 5px;
    padding: 5px;
    height: 22px;
}
.sortable.grid li {
    line-height: 80px;
    float: left;
    width: 80px;
    height: 80px;
    text-align: center;
}
.handle {
    cursor: move;
}
.sortable.connected {
    width: 200px;
    min-height: 100px;
    float: left;
}
li.disabled {
    opacity: 0.5;
}
li.highlight {
    background: #FEE25F;
}
li.sortable-placeholder {
    border: 1px dashed #CCC;
    background: none;
}
</style>

<section>
    <h1>Sortable List</h1>
    <ul id="sortable1" class="sortable list">
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
        <li>Item 4</li>
        <li>Item 5</li>
        <li>Item 6</li>
    </ul>
</section>

<section>
    <h1>Sortable Grid</h1>
    <ul id="sortable2" class="sortable grid">
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
        <li>Item 4</li>
        <li>Item 5</li>
        <li>Item 6</li>
    </ul>
</section>

<section>
    <h1>Sortable List With Disabled Items</h1>
    <ul id="sortable3" class="sortable list">
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
        <li class="disabled">Item 4</li>
        <li class="disabled">Item 5</li>
        <li class="disabled">Item 6</li>
    </ul>
</section>

<section>
    <h2>Sortable List With Handles</h2>
    <ul id="sortable-with-handles" class="sortable list">
        <li>
            <span class="handle">::</span>Item 1</li>
        <li>
            <span class="handle">::</span>Item 2</li>
        <li>
            <span class="handle">::</span>Item 3</li>
        <li>
            <span class="handle">::</span>Item 4</li>
        <li>
            <span class="handle">::</span>Item 5</li>
        <li>
            <span class="handle">::</span>Item 6</li>
    </ul>
</section>

<section>
    <h1>Connected Sortable Lists</h1>
    <ul id="sortable4" class="connected sortable list">
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
        <li>Item 4</li>
        <li>Item 5</li>
        <li>Item 6</li>
    </ul>
    <ul id="sortable5" class="connected sortable list">
        <li class="highlight">Item 1</li>
        <li class="highlight">Item 2</li>
        <li class="highlight">Item 3</li>
        <li class="highlight">Item 4</li>
        <li class="highlight">Item 5</li>
        <li class="highlight">Item 6</li>
    </ul>
</section>
<div style="clear:both;"></div>
````

````javascript
seajs.use('sortable', function(sortable) {
        new sortable({
                target: '#sortable1, #sortable2'
        })
        new sortable({
                target: '#sortable3',
                items: ':not(.disabled)'
        });

        new sortable({
                target: '#sortable-with-handles',
                handle: '.handle'
        });

        new sortable({
                target: '#sortable4, #sortable5',
                connectWith: '.connected'
        });

});
````
