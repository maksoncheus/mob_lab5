**Макаров Максим 803в2.**  
Создадим новый пустой проект, добавим в него activity. На этот activity поместим VideoView:  
![image info](/imgs/mob_lab5_1.jpg)  
Добавим папку ресурсов в проект:  
![image info](/imgs/mob_lab5_2.jpg)  
В эту папку добавим видеоролик для воспроизведения:   
![image info](/imgs/mob_lab5_3.jpg)  
В MainActivity.java инициализируем MediaController для добавления элементов управления и пропишем путь к файлу для VideoView:  
```Java
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        VideoView videoView =(VideoView)findViewById(R.id.videoView);
        MediaController mediaController= new MediaController(this);
        mediaController.setAnchorView(videoView);
        Uri uri = Uri.parse("android.resource://" + getPackageName() + "/" + R.raw.video1);
        videoView.setMediaController(mediaController);
        videoView.setVideoURI(uri);
        videoView.requestFocus();
        videoView.start();
    }
```  
Проверим работоспособность приложения:  
![image info](/imgs/mob_lab5_5.jpg)  
![image info](/imgs/mob_lab5_4.jpg)