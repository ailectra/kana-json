# Kana Data for Hanzi Writer

This is the hiragana and katakana data for [Hanzi Writer](https://github.com/chanind/hanzi-writer). This data is based on the hiragana and katakana data from [animCJK](https://github.com/parsimonhi/animCJK).

## Usage

You'll need to use a custom `charDataLoader` function to use this data in Hanzi Writer.

```
HanziWriter.create('target-div', 'あ', {
  width: 400,
  height: 400,
  charDataLoader: (char, onLoad, onError) => {
    fetch(`https://cdn.jsdelivr.net/gh/ailectra/kana-json@v0.0.1/data/${char}.json`)
      .then(res => res.json())
      .then(onLoad)
      .catch(onError);
  }
})
```
