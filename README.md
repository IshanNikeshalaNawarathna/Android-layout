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
        android:id="@+id/linearLayout"
        android:layout_width="0dp"
        android:layout_height="320dp"
        android:layout_marginStart="30dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="30dp"
        android:orientation="horizontal"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent">

        <Button
            android:id="@+id/button3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Button" />

        <Space
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1" />

        <Button
            android:id="@+id/button4"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Button" />

        <Space
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1" />

        <Button
            android:id="@+id/button5"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Button" />
    </LinearLayout>

    <LinearLayout
        android:layout_width="0dp"
        android:layout_height="320dp"
        android:layout_marginStart="30dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="30dp"
        android:layout_marginBottom="20dp"
        android:orientation="vertical"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/linearLayout"
        app:layout_constraintVertical_bias="0.612">

        <Button
            android:id="@+id/button6"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Button" />

        <Button
            android:id="@+id/button9"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Button" />

        <Button
            android:id="@+id/button10"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Button" />
    </LinearLayout>
   ```
  ![image](https://github.com/user-attachments/assets/1993a3ed-c670-40cc-9fc3-e26eaa3c59aa)


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
   ```
   ![image](https://github.com/user-attachments/assets/dd91abb3-07e5-420d-a645-5b24f1b800b8)


 ---
Happy coding! 🎉
