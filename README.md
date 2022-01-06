# Mini-Music-Player

## 개발목표 

` 음악감상을 하다가 좋아하는 노래목록으로 간단한 Music-Player를 만들어보자 라는 생각에 구현하게되었습니다`

## 사용기술

- html
- css
- javascript
- font-awesome

## 주요기능

- html, css ,javascript 들을 활용해 로컬에있는 mp3파일을사용
- 재생, 앞으로가기, 뒤로가기, 정지 버튼구현 & 소리볼륨, 원하는구간 아이콘으로 구현 & 간단한 ui


***

(All_song에 데이터들을 저장)
```
let All_song = [
  {
    name: '두 개였으면 해 - 릴러말즈',
    path: 'music/두개였으면해.mp3',
    img: 'img/img2.jpg',
    singer: '1',
  },
  {
    name: '경서예지 - 사실나는',
    path: 'music/1.mp3',
    img: 'img/img1.jpg',
    singer: '2',
  },
  {
    name: '10cm-고백',
    path: 'music/10cm-고백.mp3',
    img: 'img/장범준-고백.jpg',
    singer: '3',
  },
  {
    name: '조광일 - 가시',
    path: 'music/조광일 - 가시.mp3',
    img: 'img/조광일 - 가시.jpg',
    singer: '4',
  },
  {
    name: 'sam Ryder-Tiny Riot',
    path: 'music/sam Ryder-Tiny Riot.mp3',
    img: 'img/Sam Ryder-Tuny Riot.jpg',
    singer: '5',
  },
]
```

***

(플레이버튼, 정지, 뒤로가기, 앞으로가기, 버튼)
```
// play song
function playsong() {
  track.play()
  Playing_song = true
  play.innerHTML = '<i class="fa fa-pause" aria-hidden="true"></i>'
}

//pause song
function pausesong() {
  track.pause()
  Playing_song = false
  play.innerHTML = '<i class="fa fa-play" aria-hidden="true"></i>'
}

// next song
function next_song() {
  if (index_no < All_song.length - 1) {
    index_no += 1
    load_track(index_no)
    playsong()
  } else {
    index_no = 0
    load_track(index_no)
    playsong()
  }
}

// previous song
function previous_song() {
  if (index_no > 0) {
    index_no -= 1
    load_track(index_no)
    playsong()
  } else {
    index_no = All_song.length
    load_track(index_no)
    playsong()
  }
}
```

***

(볼륨과 , 원하는 재생구간 정보)

```
// change volume
function volume_change() {
  volume_show.innerHTML = recent_volume.value
  track.volume = recent_volume.value / 100
}

// change slider position
function change_duration() {
  slider_position = track.duration * (slider.value / 100)
  track.currentTime = slider_position
}
```

***

## 개선사항 & 느낀점
```
 - 사용자의 시점에서 불편한 ui 
 - 깔끔하지못한 기능들
 - css , javascript 이해가 좀 부족한거같다
 
 부족한 css와 javascript 를 학습하고 숙달 반복!
 ```
 
 
