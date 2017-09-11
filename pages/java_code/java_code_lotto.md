---
title: 로또번호 생성기(Random 사용)
keywords: 로또번호 생성기(Random 사용)
last_updated:
tags:
summary: "로또번호 생성기(Random 사용) 설명"
sidebar: mydoc_sidebar
permalink: java_code_lotto.html
folder: java_code
---

##### 로또번호 생성기

랜덤값을 사용한 로또번호 생성기 연습

```java
/**
 * 로또번호 생성기
 * 랜덤으로 번호 받아올때 중복된 값이있을 수 있으므로 중복체크 필요함
 * @return
 */
public int[] getLottoNumber(){
	int[] result = new int[6];
	Random random = new Random();

	for(int i = 0; i < 6; i++) {
		int num = 0;
		do{
			num = random.nextInt(45) + 1;
		}while(existNum(result, num));

		result[i] = num;
	}

	return result;
}

/**
 * nums에 num이 포함된 여부확인
 * @param nums
 * @param num
 * @return
 */
 private boolean existNum(int[] nums, int num){
 		for(int item : nums) if(item == num) return true;

 		return false;
 	}
```
