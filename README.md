import { useState } from "react";
import "./styles.css";

export default function App() {
  const [pending, setPending] = useState([
    "Learn React JS",
    "Learn Express JS",
    "Learn MongoDB"
  ]);
  const [completed, setCompleted] = useState([]);

  const showTasks = (task, index) => {
    return (
      <div>
        {task}
        <button
          onClick={() => {
            taskCompleted(index);
          }}
        >
          X
        </button>
      </div>
    );
  };

  const taskCompleted = (index) => {
    var p = [...pending];
    var c = [...completed];

    c.push(pending[index]);
    p.splice(index, 1);

    setPending(p);
    setCompleted(c);
  };

  return (
    <div>
      {/* PENDING LIST */}
      <div className="task-container">
        <h1>Pending tasks</h1>
        {pending.map(showTasks)}
      </div>

      {/* COMPLETED LIST */}
      <div className="task-container">
        <h1>Completed tasks</h1>
        {completed}
      </div>
    </div>
  );
}
