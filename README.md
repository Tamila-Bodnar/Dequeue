# Stack, Queue and Dequeue

Задания (на выбор):
- Реализовать стек, очередь и дэк на прототипах и замыканиях
- Реализовать стек через 2 класса (Stack + Element), то же и с очередью и дэком
- Добавить протокол iterable
  - см. про `next()` и [`Symbol.iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
- Сделать методы и свойства:
  - Клонирование `.clone():list`
  - Очистка `.clear()`
  - Кол-во элементов `.size`
- Реализовать события (чтоб можно было на них подписываться, но чтоб cнаружи
нельзя было делать`emit`):
  - `.on('push', (element, dequeue) => {})`
  - `.on('pop', (element, dequeue) => {})`
  - `.on('unshift', (element, dequeue) => {})`
  - `.on('shift', (element, dequeue) => {})`
  - Когда дэк опустошен `.on('drain', (dequeue) => {})`
- Взять односвязный или двусвязный список и унаследовать от него
стек, очередь и дэк
- Взять односвязный или двусвязный список и на базе их построить
стек, очередь и дэк через механизм агрегированяи (делегирования)
- Добавить в очерез таймаут ожидания в очереди `queue.timeout(msec)`
- Добавить в очередь работу с приоритетами (упорядочить очередь по приоритету)
- Реализовать очередь с приоритетами на базе массива и дерева
- Асинхронные аналоги
  - `.pop((data) => {})`
  - `.shift((data) => {})`
  - аналоги на Promise

Построение цепочек из очередей:
```js
const incoming = new Queue();
const calculating = new Queue();
const preparing = new Queue();

incoming.process(item => item).pipe(calculating);
calculating.process(item => item).pipe(preparing);
preparing.process(item => {
  console.log(item);
});
```
