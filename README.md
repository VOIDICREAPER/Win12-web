import React, { useState } from "react";
import Taskbar from "./Taskbar";
import DesktopIcon from "./DesktopIcon";
import Window from "./Window";

interface WindowType {
  id: number;
  title: string;
  content: React.ReactNode;
  isMinimized: boolean;
  zIndex: number;
}

function App() {
  const [windows, setWindows] = useState<WindowType[]>([]);
  const [nextZIndex, setNextZIndex] = useState(1);

  const openWindow = (title: string, content: React.ReactNode) => {
    const newWindow = {
      id: Date.now(),
      title,
      content,
      isMinimized: false,
      zIndex: nextZIndex
    };
    setWindows([...windows, newWindow]);
    setNextZIndex(nextZIndex + 1);
  };

  const closeWindow = (id: number) => {
    setWindows(windows.filter((win) => win.id !== id));
  };

  const minimizeWindow = (id: number) => {
    setWindows(windows.map(win => 
      win.id === id ? { ...win, isMinimized: true } : win
    ));
  };

  const focusWindow = (id: num
#import React from "react";

interface DesktopIconProps {
  name: string;
  action: () => void;
}

export default function DesktopIcon({ name, action }: DesktopIconProps) {
  return (
    <div
      onClick={action}
      style={{
        width: 90,
        height: 90,
        margin: 12,
        backgroundColor: "transparent",
        color: "white",
        display: "flex",
        flexDirection: "column",
        alignItems: "center",
        justifyContent: "center",
        cursor: "pointer",
        borderRadius: "12px",
        padding: "8px",
        transition: "all 0.3s cubic-bezier(0.4, 0, 0.2, 1)",
        fontSize: "11px",
        fontWeight: "500",
        textAlign: "center",
        lineHeight: "1.2",
        backdropFilter: "blur(10px)",
        border: "1px solid rgba(255, 255,
 Win12-web
