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
* Shell
* Merge
* Quick
* Heap 