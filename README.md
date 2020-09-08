# Word Search game custom view

### Summary

Word search custom view for android, includes an interactive board of characters which can be initialised using your custom algorithm to generate a 2D array of characters including hidden words to be found.


### Download

You can use Gradle:

```
dependencies {
	implementation 'com.ayush_khanna:wordsearch:0.1'
}
```

or Maven:

```
<dependency>
  <groupId>com.ayush_khanna</groupId>
  <artifactId>wordsearch</artifactId>
  <version>0.1</version>
  <type>pom</type>
</dependency>
```

### Use

```
wordsGrid = findViewById(R.id.wordsGrid);

// to set font
wordsGrid.setTypeface(FontManager.getTypeface(this, FontManager.POYNTER));

// create a 10x10 grid of characters which includes words to be found
wordsGrid.setLetters(new char[][] {
        "XJAVADFPNL".toCharArray(),
        "WSFAKMQZRP".toCharArray(),
        "QWJRTOLNDY".toCharArray(),
        "MIRIUBTNVT".toCharArray(),
        "JFPAWILLGH".toCharArray(),
        "STBBNLIZIO".toCharArray(),
        "GCRLJEUQFN".toCharArray(),
        "JTZEVIYZMW".toCharArray(),
        "PEWQCHDPJK".toCharArray(),
        "OBJECTIVEC".toCharArray()
});

// words with their respective starting and ending X and Y values in the grid
wordsGrid.setWords(
        new Word("SWIFT", false, 1, 1, 5, 1),
        new Word("KOTLIN", false, 1, 4, 6, 9),
        new Word("OBJECTIVEC", false, 9, 0, 9, 9),
        new Word("VARIABLE", false, 0, 3, 7, 3),
        new Word("JAVA", false, 0, 1, 0, 4),
        new Word("MOBILE", false, 1, 5, 6, 6),
        new Word("PYTHON", false, 1, 9, 6, 9));

// callback when a word is found
wordsGrid.setOnWordSearchedListener(new WordSearchView.OnWordSearchedListener() {
    @Override
    public void wordFound(String word) {
        Toast.makeText(MainActivity.this, word + " found", Toast.LENGTH_SHORT).show();
    }
});
```

