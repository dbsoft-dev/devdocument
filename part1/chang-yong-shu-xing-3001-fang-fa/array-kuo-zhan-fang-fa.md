# Array 数组扩展方法

* #### IndexOf\(\)

  * ##### 作用：获取元素的索引值；存在重复的元素，将获取重复元素的第一个所在的索引值；元素不存在时，返回-1；
  * ##### 示例：
  * ```js
    //返回值为3；
    [1,2,3,4,5,4].IndexOf(4);
    ```

* #### Remove\(el\)

  * ##### 作用：移除数组中的某个元素，参数el为数组中的元素，元素不在数组中时，数组将不移除任何元素，存在重复的元素，只移除第一个找到的元素；
  * ##### 示例：
  * ```js
    //数组移除元素4后变成[1,2,3,5,4]
    [1,2,3,4,5,4].Remove(4);
    ```

* #### RemoveAt\(index\)

  * ##### 作用：移除指定索引值的元素；
  * ##### 示例：
  * ```js
    //移除后数组变为[1,2,3,4,4]；
    [1,2,3,4,5,4].RemoveAt(4);
    ```

* #### Clear\(\)

  * ##### 作用：清空数组所有元素；
  * ##### 示例：
  * ```js
    //数组清空后变成[]
    [1,2,3,4,5,4].Clear();
    ```

* #### Add\(el\)

  * ##### 作用：在数组后添加元素；
  * ##### 示例：
  * ```js
    //数组添加元素后后变成[1,2,3,4,5,4,'hello']
    [1,2,3,4,5,4].Add('hello');
    ```

* #### Insert\(val, tval\)

  * ##### 作用：在指定元素前插入元素，参数val为需要插入的元素，参数tval为数组中已存在的元素；
  * ##### 示例：
  * ```js
    //插入元素后数组变成[1,9,2,3,2,4,5,4]
    [1,2,3,2,4,5,4].Insert(9,2);
    ```

* #### InsertAt\(index,val\)

  * ##### 作用：在指定索引位置插入元素，参数index为索引位置，数值；val为需要插入的元素；
  * ##### 示例：
  * ```js
    //插入后数组变为[10,1,2,3,4,5,4]；
    [1,2,3,4,5,4].InsertAt(0,10);
    ```

* #### Clear\(\)

  * ##### 作用：清空数组所有元素；
  * ##### 示例：
  * ```js
    //数组清空后变成[]
    [1,2,3,4,5,4].Clear();
    ```



