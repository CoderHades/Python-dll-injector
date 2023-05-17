# Python-dll-injector

We import the necessary modules:

tkinter for creating the GUI application
ctypes for loading and manipulating DLLs
filedialog and messagebox from tkinter for file browsing and displaying messages
Combobox from tkinter.ttk for creating a dropdown box
We define two functions:

browse_dll(): This function opens a file dialog for selecting a DLL file and updates the entry field with the selected file path.
inject_dll(): This function retrieves the selected application and DLL path, loads the DLL using ctypes, gets the process ID of the selected application, and performs the DLL injection.
We create the main application window using tkinter.Tk() and set its title.

We define the style for the application using tkinter.ttk.Style(). In this case, we set the theme to 'clam' and configure the styles for TLabel, TButton, and TCombobox with custom font, foreground, and background settings.

We create a label and a dropdown box for selecting the target application. We iterate through the list of active processes using psutil.process_iter() to populate the dropdown box with the process names.

We create a button labeled "Browse DLL" that calls the browse_dll() function when clicked.

We create a label and an entry field for displaying the selected DLL path.

We create a button labeled "Inject DLL" that calls the inject_dll() function when clicked.

Finally, we start the application's main event loop using root.mainloop(), which keeps the application running until it is closed.

When the user selects an application from the dropdown box, the selected application's process ID is retrieved. When the user clicks the "Browse DLL" button, they can select a DLL file. The selected DLL path is then displayed in the entry field. When the user clicks the "Inject DLL" button, the selected DLL is loaded using ctypes, and the injection process is performed by opening the target application's process and calling FreeLibrary to inject the DLL.

Throughout the process, messagebox is used to display success or error messages to the user
