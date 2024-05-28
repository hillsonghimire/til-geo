##  Filter from `ImageCollection` in GEE

#### ISSUE
```
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-17-cc314145052e> in <cell line: 1>()
----> 1 display(SemiAnnualCol[2])
---------------------------------------------------------------------------

TypeError: 'ImageCollection' object is not subscriptable, how to grab second element
```

* If the `ImageCollection` type directly subscripting is not possible in earth engine as how we do with `list` objects.

#### Solution
1. Convert the ImageCollection to a list: Use the `toList` method to convert the ImageCollection to a list.
2. Get the second element from the list: Use the `get` method to retrieve the element from the list.


```
# Assuming SemiAnnualCol is your ImageCollection
image_list = SemiAnnualCol.toList(SemiAnnualCol.size())
second_image = ee.Image(image_list.get(1))

# To display the second image, you would typically use it in further processing or visualization
print(second_image.getInfo())
```