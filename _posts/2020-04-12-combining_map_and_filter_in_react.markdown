---
layout: post
title:      "Combining map() And filter() In React "
date:       2020-04-13 02:18:30 +0000
permalink:  combining_map_and_filter_in_react
---

In this blog, I am going to focus on how we can combine map and filter methods together in react. 
I am going to show an example from my final project at Flatiron school on how we can combine these two methods together. For this project I created an application that track the calibration tools due date at the production floor. When I was working in this project I was stuck on creating a report that filter only the tools that the calibration due date were passed. So I submitted my project without this report because I didn't have enough time. After I was finish from my review I was able to create this report by combining filter and map methods together. First I used filter function, which it’s allowing me get only the tools that the expatriation due date less than today date. After filter I used map function.  Here is the code: 
 

```
function ToolsDueDate(props) {

  let today = new Date();
  let dd = today.getDate();
  let mm = today.getMonth();
  let yyyy = today.getFullYear();
  if (dd < 10) {
    dd = '0' + dd;
  }
  if (mm < 10) {
    mm = '0' + mm;
  }
  today = yyyy + '-' + mm + '-' + dd;

  const toolsIndex = props.tools.**filter**(tool => tool.expiration_due_date <= today).**map**(tool => {
      return <ToolDueDate key={tool.id} tool={tool} />;
    });

  return (
    <ul>
      <h2 className="toolList"> Tool Past Due Date:</h2>
      <hr></hr>
      {toolsIndex}
    </ul>
  );
}
```


