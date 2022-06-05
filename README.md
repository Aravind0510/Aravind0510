import { useState } from "react";

export default function App() {
  const [pending, setPending] = useState(["Learn React JS", "Learn Express JS", "Learn MongoDB"]);
  const [completed, setCompleted] = useState([]);

  return (
    <div>
      <button>change a</button>
      {/* PENDING LIST */}
      <div>
        <h1>Pending tasks</h1>
        {pending}
      </div>

      {/* COMPLETED LIST */}
      <div>
        <h1>Completed tasks</h1>
        {completed}
      </div>
    </div>
  );
}
