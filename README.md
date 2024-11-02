# Power Apps Component Framework Control: `pacftest`

This repository contains a sample Power Apps Component Framework (PCF) control designed for demonstrating basic functionality in a custom control. Below are details on how to set up, use, and understand the control.

## Overview

The `pacftest` control provides a simple interface where users can view a name, edit it, and save changes. It uses standard HTML elements for rendering and responds to user interactions via JavaScript event listeners.

## Features

- **Display Name**: Shows the name passed from the data source.
- **Edit Mode**: Allows the user to edit the name by clicking an "Edit" button which transforms into a "Save" button.
- **Save Functionality**: Updates the name when the "Save" button is clicked, and reflects changes in real-time.

## Code Structure

```typescript
export class pacftest implements ComponentFramework.StandardControl<IInputs, IOutputs> {
    // Constructor and lifecycle methods
    constructor();
    public init(context: ComponentFramework.Context<IInputs>, notifyOutputChanged: () => void, state: ComponentFramework.Dictionary, container:HTMLDivElement): void;
    public updateView(context: ComponentFramework.Context<IInputs>): void;
    public getOutputs(): IOutputs;
    public destroy(): void;
    
    // Private members and methods
    private context: ComponentFramework.Context<IInputs, ComponentFramework.IEventBag>;
    private notifyOutputChanged: () => void;
    private container: HTMLDivElement;
    private isEditMode: boolean;
    private name: string | null;
    private buttonClickHandler: EventListener;
    private buttonClick(): void;
}