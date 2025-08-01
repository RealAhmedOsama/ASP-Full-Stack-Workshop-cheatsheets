# ⚡ jQuery 3.x Quick-Ref Cheat Sheet – *Rich Edition*

> **Scope:** The **90 %** of jQuery you actually use every day—selectors, DOM edits, event handling, effects, **AJAX (incl. table-row injection)**, forms, and utilities.
---

## 1️⃣ Bootstrapping

```html
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script>
  $(function () {                // DOM ready shorthand
    console.log("DOM parsed");   // => logs on load
  });
</script>
```

---

## 2️⃣ Selectors & Traversal 🔍

| Goal                 | Snippet                     | Returns / Notes           |
| -------------------- | --------------------------- | ------------------------- |
| **ID**               | `$("#logo")`                | jQuery object (1 element) |
| **Class**            | `$(".item")`                | All `.item` nodes         |
| **Attribute**        | `$("input[type=password]")` | Matching inputs           |
| **Nth in list**      | `$("ul li").eq(2)`          | 3rd `<li>`                |
| **Closest ancestor** | `$(".btn").closest("form")` | Parent `<form>`           |
| **All siblings**     | `$("#row").siblings()`      | Bro & sis nodes           |

```js
$("#menu li")             // find <li>
      .first()            // → first li
      .css("color","red");// style it
```

---

## 3️⃣ DOM Manipulation 🛠️

```js
// HTML / Text
$("#msg").html("<b>Saved</b>");   // sets innerHTML → jQ object
$("#msg").text("Safe text");      // escapes HTML

// Insert
$("<li>New</li>").appendTo(".list");     // end of list
$("<li>First</li>").prependTo(".list");  // start of list
$(".notice").insertAfter("#header");     // after specific node

// Clone & remove
var copy = $("#card").clone().addClass("copy").appendTo("#cards");
$("#obsolete").remove();         // deletes node(s)
$("#log").empty();               // clears children only
```

---

## 4️⃣ **Table Row Injection** (from JSON) 📋

```html
<table id="userTbl" class="table">
  <thead><tr><th>ID</th><th>Name</th><th>Email</th></tr></thead>
  <tbody></tbody>
</table>
```

```js
function addRow(u){
  $("#userTbl tbody").append(`
    <tr>
      <td>${u.id}</td>
      <td>${u.name}</td>
      <td>${u.email}</td>
    </tr>
  `);                // → row appears instantly
}

// Example usage
addRow({id:1,name:"Ali",email:"ali@mail.com"});
```

---

## 5️⃣ Attributes, Data & CSS 🎨

```js
// Attribute
$("img.hero").attr("alt","Hero Pic");      // sets alt

// Data-attributes (auto camelCase)
$("#btn").data("state","on");              // write
$("#btn").data("state");   // => "on"

// Classes
$("#box").addClass("active large")         // multiple
         .toggleClass("hidden");           // switch

// Inline CSS (object form = single repaint)
$(".panel").css({height:200,width:300});   // px assumed
```

---

## 6️⃣ Events ⚡

```js
// Standard
$("#save").on("click", saveData);          // attach
$("#save").off("click", saveData);         // detach

// Delegation (works on future elems)
$(document).on("click", ".delete", function () {
  $(this).closest("tr").remove();          // remove row
});

// Shorthand
$("a.external").click(function(e){
  e.preventDefault();
  window.open(this.href);
});
```

---

## 7️⃣ Effects / Animation 🎞️

```js
$("#box").hide();          // instant
$("#box").show(400);       // ms
$("#box").fadeOut("slow"); // fade
$("#box").slideToggle(300);// accordion

// Custom numeric animation
$("#bar").animate({width:"75%"}, 800, "swing"); // progress bar
```

---

## 8️⃣ AJAX Essentials 🌐

### 8.1 Quick Helpers

```js
// GET JSON
$.getJSON("/api/users/1", function (u) { 
  addRow(u);                         // inject into table
});
```

### 8.2 Full-Control `$.ajax` + Promises

```js
$.ajax({
  url: "/api/users",
  method: "GET",
  dataType: "json",
  timeout: 5000          // ms
}).done(function(list){      // success
     $.each(list, addRow);   // fill table
}).fail(function(xhr){
     alert("Load failed: "+xhr.status);
}).always(function(){
     $("#spinner").hide();   // UI cleanup
});
```

### 8.3 POST (JSON)

```js
$.ajax({
  url:"/api/save",
  method:"POST",
  contentType:"application/json",
  data: JSON.stringify({title:"Hi"}),
}).then(function(r){          // promise style
  console.log(r.status);      // => "ok"
});
```

---

## 9️⃣ Forms & Inputs 📝

```js
// Value getter / setter
var name = $("#name").val();          // => current text
$("#age").val(30);                    // sets

// Serialize whole form
var query = $("#userForm").serialize(); // "name=Ali&age=30"

// Disable
$("button[type=submit]").prop("disabled", true);
```

---

## 🔟 Utilities 🧰

```js
$.trim("  text  ");            // => "text"
$.type([]);                    // => "array"
$.isNumeric("123");            // => true
$.inArray("b", ["a","b"]);     // => 1

// Iteration (objects & arrays)
$.each({a:1,b:2}, function(k,v){ console.log(k,v); });

// Deep copy
var clone = $.extend(true, {}, original);
```

---

## 1️⃣1️⃣ Chaining ✔️ & Performance Tips

```js
// Chain to minimise DOM touches
$("#msg")
  .removeClass("error")
  .addClass("info")
  .text("Saved!")
  .fadeIn(200);

// Cache expensive selectors
var $rows = $("#userTbl tbody tr");
$rows.filter(":odd").addClass("alt");
```

---

### 💡 Best-Practice Recap

1. **One selector, many actions:** chain for speed.
2. **Event delegation** for dynamically added elements (`.on('click', '.child', fn)`).
3. Always **handle `.fail()` / `.catch()`** on AJAX to avoid silent bugs.
4. **Serialize** forms instead of manual field collection.
5. **Keep business logic out of the UI layer**—use callbacks or promises to separate concerns.
