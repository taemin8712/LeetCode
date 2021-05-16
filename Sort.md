# Sort
>> 기본 : 오름차순 기준으로 정리한 내용
	* Insrt 
	> 앞에서부터 차례대로 이미 정렬된 배열 부분과 비교
	<li>
	1. 두번째 자료부터 시작하여 그 앞의 자료와 비교후 정렬
	</li>
	<li>2. n-1! 순으로 	ex) 2번쨰 자료는 1번쨰 자료와 비교, 3번쨰는 1,2 번째 자료와 비교 ...</li>
	<li>3. 첫 key는 두번째로하여 시작</li>

<table>
<th>
** 장점**
<ol>
<li>1. 안정적인 방법</li>
<li>2. 레코드 수가 적을때 사용 </li>
<li>3. 어느정도 정렬이 된 상태라면 매우 효율적이다.
</li>
</ol
</th>
<th>
**단점**
<ol>
<li>1. 많은 레코드들의 이용을 필요로 한다.</li>
<li>2. 레코드 수가 많을시에는 부적합하다.</li>
</ol>
</th>
</table>
*** 시간복잡도 (Time Complexity)
* 최선 : O(n)
* 최악 : O(n^2) --> 자료의 순서가 역순일때



<img src="https://gmlwjd9405.github.io/images/algorithm-insertion-sort/sort-time-complexity.png" alt="" />


* Selection

* Bubble 

</br>
</p>



* Merge
* Shell
>분할 정복 알고리즘. (divide & conquer)
 <ol>
 	<li>
 		Divde : 입력된 배열을 2개의 부분 배열로 분할
 	</li>
 	<li>
 		Conquer : 2개롤 나눈 배열을 정렬한다. 크기가 작지 않다면 부분 배열을 다시 분할 하여 분할 정복 방법을 적용한다. (순환 호출 == 재귀 호출 )
 	</li>
 	<li>
 		 COmbine : 정렬된 부분 배열을 다시 하나의 배열로 합병
 		 ** 추가적인 리스트가 필요.
 	</li>
 </ol>
 
** Code in Swift **
// _ array : unsorted Array
func mergeSort<T: Comparable>(_ array: [T]) -> [T] {
  guard array.count > 1 else { return array }
  // 중간 인자 생성
  let middleIndex = array.count / 2
  //0.. 중간인자까지 sort 
  let leftArray = mergeSort(Array(array[0..<middleIndex]))
  //중간.. 끝까지 sort
  let rightArray = mergeSort(Array(array[middleIndex..<array.count]))
//	왼쪽,오른쪽 정렬된 배열 리턴
  return merge(leftArray, rightArray)
}
//
func merge<T: Comparable>(_ left: [T], _ right: [T]) -> [T] {
  var leftIndex = 0
  var rightIndex = 0

  var orderedArray: [T] = []

	// 각 인자가 배열 숫자보다 작을떄까지만 
  while leftIndex < left.count && rightIndex < right.count {

    let leftElement = left[leftIndex]
    let rightElement = right[rightIndex]

    if leftElement < rightElement {
      orderedArray.append(leftElement)
      leftIndex += 1
    } else if leftElement > rightElement {
      orderedArray.append(rightElement)
      rightIndex += 1
    } else {
      orderedArray.append(leftElement)
      leftIndex += 1
      orderedArray.append(rightElement)
      rightIndex += 1
    }
  }

  while leftIndex < left.count {
    orderedArray.append(left[leftIndex])
    leftIndex += 1
  }

  while rightIndex < right.count {
    orderedArray.append(right[rightIndex])
    rightIndex += 1
  }

  return orderedArray
}


* Quick
* Heap 