---
title: List Class(Generic 활용)
keywords: List Class(Generic 활용)
last_updated:
tags:
summary: "List Class(Generic 활용) 설명"
sidebar: mydoc_sidebar
permalink: java_code_list_class.html
folder: java_code
---

### Generic을 사용하여 List 클래스 만들기

```java
package com.daehoshin.java.generic;


/**
 * 제네릭을 사용하여 List 만들기
 *
 * @author daeho
 *
 */
public class DHList<T> {
	private Object[] list;

	/**
	 * 값을 넣지 않은 상태에서 사이즈 등의 체크를 할수 있기 때문에
	 * 저장소를 초기화 해주는 작업이 필요하다
	 */
	public DHList(){
		list = new Object[1];
	}

	/**
	 * list는 갯수보다 항상 한개많기 때문에 배열의 -1개를 리턴
	 * @return
	 */
	public int size(){
		return list.length - 1;
	}

	/**
	 * list보다 1개큰 tempList를 만들어 그쪽에 저장하여 list에 넣어줌
	 * @param item
	 */
	public void add(T item){
		Object[] tempList = new Object[list.length + 1];
		for(int i = 0; i < list.length; i++){
			tempList[i] = list[i];
		}
		tempList[list.length - 1] = item;
		list = tempList;
	}

	/**
	 * list보다 1개큰 tempList를 만들어 그쪽에 지정된 인덱스위치에 추가하여 list에 넣어줌
	 * @param index
	 * @param item
	 */
	public void add(int index, T item){
		Object[] tempList = new Object[list.length + 1];

		int cnt = 0;
		for(int i = 0; i < list.length; i++){
			if(i == index){
				tempList[cnt] = item;
				cnt++;
			}
			tempList[cnt] = list[i];
			cnt++;
		}
		list = tempList;
	}

	/**
	 * list를 돌며 지정한 index를 제외한 목록일 tempList에 반영하여 list로 다시 옴김
	 * @param index
	 */
	public void remove(int index){
		Object[] tempList = new Object[list.length - 1];

		int cnt = 0;
		for(int i = 0; i < list.length; i++){
			if(i == index) continue;
			tempList[cnt] = list[i];

			cnt++;
		}
		list = tempList;
	}

	/**
	 * list를 돌며 지정한 item을 제외한 목록일 tempList에 반영하여 list로 다시 옴김
	 * @param item
	 */
	public void remove(T item){
		Object[] tempList = new Object[list.length - 1];

		int cnt = 0;
		for(int i = 0; i < list.length; i++){
			if(list[i] == item) continue;
			tempList[cnt] = list[i];

			cnt++;
		}
		list = tempList;
	}

	/**
	 * 지정한 인덱스의 아이템을 리턴
	 * @param index
	 * @return
	 */
	public T get(int index){
		return (T) list[index];
	}
}
```
