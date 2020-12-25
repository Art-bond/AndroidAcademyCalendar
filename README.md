# AndroidAcademyCalendar
📆The app shows the possibilities of working with the calendar and database (Room)


Приложение отображающее список мероприятий

Вместо двух Activity, создадим два Fragmenta

2. Один из фрагментов для удобства будет :
BottomSheetDialogFragment
чтобы все было видно на одном экране

3. Свяжем оба фрагмента в nav_graph.xml

добавим Arguments для передачи данных между Фрагментами

4. Добавим простую БД для хранения списка данных


        @Dao
        interface EventDao {       
          @Query("SELECT * FROM event")
          fun getAll(): LiveData<List<Event>>

          @Query("SELECT * FROM event WHERE id = :id")
          suspend fun get(id: Long): Event

          @Insert
          suspend fun insert(event: Event): Long

          @Delete
          suspend fun delete(event: Event)

          @Update
          suspend fun update(event: Event)
          }
    

5. Адаптер и Data class оставим практически без изменений


https://telegra.ph/D3-2-Android-Academy-11-05

![Alt-Text](https://telegra.ph/file/e39eb8f466afd5f36f26f.png)
![Alt-Text](https://telegra.ph/file/118b9549116429212ff0e.png)
![Alt-Text](https://telegra.ph/file/0f038c2c4c427fd5d9e9e.png)
![Alt-Text](https://telegra.ph/file/581c1777d0563042d1852.png)
