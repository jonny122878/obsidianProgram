

- Aggregate、Where其Enumerable動作是元素間互相運算，衍生衝突:
  - 元素值為null
	[[Enumerable Aggregate exception]]7.
	[[SQL Aggregate exception]]4.

  - 型態之間不同比較
	[[SQL Aggregate exception]]2.
	[[Enumerable Where exception]]1.
	[[SQL Where exception]]3.

- Select其Enumerable動作是元素本身之間再次投射，衍生衝突:

- Enumerable本身為空，做任何動作，衍生衝突:
	[[Enumerable Aggregate exception]]1.、3.
	[[SQL Aggregate exception]]1.
	[[Enumerable Select exception]]1.

