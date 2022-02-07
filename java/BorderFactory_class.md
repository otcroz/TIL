### BorderFactory
다양한 형태의 경계선 지원

```
	private void makeBorder(JPanel panel, String title_name) {
		Border etched = BorderFactory.createEtchedBorder();
		TitledBorder title = BorderFactory.createTitledBorder(etched, title_name);
		title.setTitlePosition(TitledBorder.TOP);
		panel.setBorder(title);
	}
```

```BorderFactory.createEtchedBorder();``` : 보더의 종류를 생성하는 함수<br>
- createXXXBorder 종류
   ```createLineBorder()```, 
   ```createraisedEtchedBorder()```,
   ```createLoweredEtchedBorder()```,
   ```createRaisedBevelBorder()```,
   ```createLoweredBevelBorder()```,
   ```createTitleBorder()```,
   ```createEtchedTitleBorder()``` <br><br>
   
```title.setTitlePosition(TitledBorder.TOP)``` : Border 내에 있는 title의 위치를 설정하는 함수<br>
```panel.setBorder(title);``` : 패널에 TitleBorder을 붙여줌 
