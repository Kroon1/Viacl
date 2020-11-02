# Příklad použití
var saga = new Saga({});

saga

  .addTask(
  
    { id: "createOrder", transaction: fn1, compensation: cp1 })
    
  .addParallelTasks(
  
    { id: "bookAuto", transaction: fn2 },
    
    { id: "buyTicket", transaction: fn3, compensation: cp3 }
    
  )
  .addTask(
  
    { id: "reserveHotel", transaction: fn4, compensation: cp4 });
  
saga.run({ startAt: dateStart, endAt: dateEnd });
