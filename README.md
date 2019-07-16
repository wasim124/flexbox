# Flexbox

## Introduction

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/banner.png)

I hope we all have the basic knowledge of HTML and CSS now. In the last few days, we have learned how to position an element in a page according to the layout. We have learned about the floats and inline-block as well as a few advanced properties to position the elements. I am sure you all have been through the pains while working with the floats and a few other properties of positioning. Because I also have been the same problem as you guys are facing now.

We always had been doing all those hackish methods of floats, table displays, inline-block for positioning the elements. But we can ditch all the hacky methods now. We are ready to go with flexbox. Flexbox is one of the most interesting topics of CSS. I am sure while working flexbox you will enjoy and will have a lot of fun.

## Topics of the day

1. What is flexbox?
2. How does the flexbox model work?
3. Flex Wrap
4. Flex ordering
5. Flexbox Alignment

- Justify Content
- Align Items
- Align Content
- Align Self

6. Flex Sizing with flex Property

## 1. What is flexbox?

Flexbox provides us a more efficient way to lay out elements. It gives us the ability to align the items and distribute space among the items in a container - even though the size of the elements are unknown or dynamic. With the flexbox we get the power of flexibility(as the word flex says) in order fill the available space. So that elements can easily accommodate according to the size of screens. In a flexbox container, item expands to fill the free space as well as shrinks to prevent overflow.

## 2. How does the flexbox model work?

Flexbox model comes with some sets of properties and values. In that few properties can be applied to parent container and few can be applied only on children items. So to make use of those flexbox model properties and values we will have to go into the zone of flexbox. So how do we go into that?

To do so, we start with `display: flex` property and value. We set the parent's styles as `display: flex`. Once we do so we are in the zone of the flexbox model. Now we can get benefitted with the properties of the flexbox model. Without setting the parent element's style as `display: flex`, we cannot make use of any property related to the flexbox model.

So what happens we set the parent's style as `display: flex`. Let's check it out:

```
  <div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  * {
    margin: 0;
    padding: 0;
  }
  .container {
    display: flex;
    background: #FAFFFC;
    border: 5px solid #182945;
  }
  .item {
    background: #9EDDEB;
    padding: 40px 50px;
    font-size: 34px;
    margin: 10px;
  }

```

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/intro.png)

This is how a simple flexbox model looks like. Once we say display flex to a parent element, it automatically becomes `flex container` and the children inside it becomes `flex-item`.

### Terminology:

While working with flexbox model, there are few basic terminologies that you need to keep in mind. For example `flex container and flex-item`, as I have used just a few lines above. I will explain all the terminologies as it comes in our flow.

For now, let's see what is `flex container and flex-item`?

#### 1. Flex Container

The Parent element where you need to apply 'display: flex'.

#### 2. Flex Items

The children elements inside the flex container.

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/container-item.png)

If you remember in the beginning we talked that the flexbox model comes with some sets of properties and values, in which few belongs to parent container and few can be applied to the children items. So here we have few properties that can be applied to the 'flex container' and few can be applied to 'flex-item'. Let's see what are properties that can be applied to flex container, we will discuss them in detail and then after will move into the properties of flex-item.

## 3. Understanding the Flex Container properties.

According to the flexbox model, the properties that can be applied to flex containers are:

`Display, flex-direction, flex-wrap, flex-flow, justify-content, align-items, align-content`.

### A. Display:

The display property is to activate the flexbox model zone as we have discussed in the above section. Remember I told you that without setting the `display: flex`, you cannot get into the flexbox model zone, and therefore you cannot be benefited with the flexbox properties and values. This is the property from where the real magics get started.

The display property can take two values:

```
display: flex || inline-flex;
```

The `display: flex` works normally as we have seen earlier.

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/intro.png)

The `display: inline-flex` is similar to inline elements, but this is for the inline version of the flex container so that the container takes the space according to the content in it.

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/inline-flex.png)

### B. Flex Direction

Flex direction property determines the direction of the item in which they will lay down. By default when we set the property as 'display: flex', all the item lay down one by one horizontally. Instead of saying items lay down horizontally, rather I must say items lay down on the 'main-axis'. Now here is the time to discuss the two terminologies i.e. 'main-axis' and 'cross-axis'.

#### Terminology(main-axis and cross-axis)

Actually, in the flexbox model, there are two axes: 'main-axis' and 'cross-axis'. Here we don't have something like 'horizontal-axis' and 'vertical-axis'.

##### 1. Main Axis

The 'main-axis' in the flexbox model is the primary axis along which the items are laid out in the flex container. By default, the 'main-axis' feels like "horizontal direction", from left to right.

##### 2. Cross Axis

The 'cross-axis' goes perpendicular to the 'main-axis'. It feels like "vertical direction", top to bottom.

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/axis.png)

The important point to note here is that the 'main-axis' is not necessary to remail always in the horizontal direction. We can anytime interchange the direction of axes with the 'flex-direction' property. Now let's get back to the 'flex-direction' property.

The flex-direction property can accept four values:

flex-direction: row || column || row-reverse || column-reverse;

#### Row

flex-direction: row;

This is the default value for 'flex-direction' property. After applying this property you won't find any changes.

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/row.png)

#### Column

flex-direction: column;
After this value, all the item in the flex-container will lay down top to bottom. This value changes the direction of the axes in the flexbox model. The main-axis takes the place of 'cross-axis' and the 'cross-axis' takes the place of 'main-axis'.

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/column.png)

#### Row-reverse

flex-direction: row-reverse;

The 'row-reverse' is similar to 'row' but this all the item will sit from right to left means in the opposite direction.

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/row-reverse.png)

#### Column-reverse

flex-direction: column-reverse;

The 'column-reverse' is also opposite to the 'column'. The item will lay down from bottom to top.

![alt text](https://raw.githubusercontent.com/AltCampus/flexbox/master/media/column-reverse.png)

## Additional Resources

1. https://css-tricks.com/snippets/css/a-guide-to-flexbox/

2. https://flexbox.io/
