## LayoutManager
Позволяет настроить разметку списка. Есть три вида:
- `LinearLayoutManager`- дочерние элементы размещаются вертикально или горизонтально (как список видео в мобильной версии YouTube).
	- `LinearLayoutManager(context: Context!)`
	- `LinearLayoutManager(context: Context!, orientation: Int, reverseLayout: Boolean)`: `reverseLayout` - `reverseLayout` - при true начинается с конца.
	- `LinearLayoutManager(context: Context!, attrs: AttributeSet!, defStyleAttr: Int, defStyleRes: Int)`: `attrs` - описывается layout в виде XML.
- `GridLayoutManager` - дочерние элементы размещаются по сетке (как в Instagram*).
	- `GridLayoutManager(context: Context!, spanCount: Int)`: `spanCount` - номер столбцов (сетка расширяется вертикально).
	- `GridLayoutManager(context: Context!, attrs: AttributeSet!, defStyleAttr: Int, defStyleRes: Int)`
	- `GridLayoutManager(context: Context!, spanCount: Int, orientation: Int, reverseLayout: Boolean)`
- `StaggeredGridLayoutManager` - неравномерная сетка (как в Pinterest). 
	- `StaggeredGridLayoutManager(spanCount: Int, orientation: Int)`: `spanCount` - номер столбцов или строк (зависит от ориентации).
	- `StaggeredGridLayoutManager(context: Context!, attrs: AttributeSet!, defStyleAttr: Int, defStyleRes: Int)`

## ItemDecoration
Позволяет настроить внешний вид (разделители, полосы прокрутки). Сам по себе этот класс абстрактный, с тремя методами:
 - `onDraw(@NonNull Canvas c, @NonNull RecyclerView parent, @NonNull RecyclerView.State state)` - для отрисовки перед элементами. `c` - Canvas, на котором происходит отрисовка, `state` - текущее состояние (например, положение относительно начала списка или выделенный элемент).
 - `onDrawOver(@NonNull Canvas c, @NonNull RecyclerView parent, @NonNull RecyclerView.State state)` - для отрисовки после элементов.
 - `getItemOffsets(@NonNull Rect outRect, @NonNull View view, @NonNull RecyclerView parent, @NonNull RecyclerView.State state)` - для выставления отступов. `outRect` - прямоугольник, в который должен помещаться элемент.

## ItemAnimation
Позволяет накладывать анимации при появлении, изменении и исчезновении элементов.

\*Запрещен на территории РФ
