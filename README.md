# Android Layouts and Usage

This repository is a collection of examples and notes for learning Android layouts and their usage.

## Overview

Android layouts are used to define the user interface of an application. They determine the structure, design, and alignment of components like buttons, text, and images on the screen. This project focuses on understanding the following layout types:

- **LinearLayout**: Arranges views in a single row or column.
- **RelativeLayout**: Positions views relative to each other or the parent container.
- **ConstraintLayout**: A flexible layout that allows positioning and sizing based on constraints.
- **FrameLayout**: A container for a single child view, used for overlaying elements.
- **TableLayout**: Organizes views into rows and columns.
- **GridLayout**: Divides the screen into a grid structure.

## Key Concepts

1. **Attributes**: 
   - `layout_width` and `layout_height`
   - `layout_gravity` and `gravity`
   - `padding` and `margin`

2. **Hierarchy**:
   - Nesting layouts.
   - Using a `ViewGroup` as the parent container.

3. **Best Practices**:
   - Use `ConstraintLayout` for complex designs.
   - Minimize nested layouts to improve performance.

## Examples

- **LinearLayout Example**:
  
  ```xml
  <LinearLayout
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      android:orientation="vertical">
      <TextView
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:text="Hello, World!" />
      <Button
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:text="Click Me" />
  </LinearLayout>

- **Frame Layout Example**:
  
  Tree type access the Frame layout
  
   ```Java
        Button button2 = findViewById(R.id.button2);
        Button button1 = findViewById(R.id.button);

        button2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                button2.setVisibility(View.INVISIBLE);
                button1.setVisibility(View.VISIBLE);
            }
        });


        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                button1.setVisibility(View.INVISIBLE);
                button2.setVisibility(View.VISIBLE);
            }
        });
        
        
        OR
        
        Button button2 = findViewById(R.id.button2);
        Button button1 = findViewById(R.id.button);

        button2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                button1.bringToFront();
            }
        });


        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                button2.bringToFront();
            }
        });
        
        OR
        
        
        Button button3 = findViewById(R.id.button7);
        Button button4 = findViewById(R.id.button8);

        button3.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                button3.setVisibility(View.GONE);
                button4.setVisibility(View.VISIBLE);
            }
        });

        button4.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                button4.setVisibility(View.GONE);
                button3.setVisibility(View.VISIBLE);
            }
        });

 ---
Happy coding! 🎉
