# Bill Splitter

A responsive, browser-based bill splitting tool for restaurant meals. Bill Splitter helps a group divide a restaurant bill according to the food each person consumed, while accounting for CGST, SGST, and restaurant round-off.

**Live website:** [https://aswins404.github.io/BillSplitter](https://aswins404.github.io/BillSplitter)  

## Project Introduction

Bill Splitter is designed to make splitting restaurant bills clearer and more accurate than simply dividing the final amount equally. Enter the restaurant bill details, add the food items and their quantities, then assign each item to the people who shared it. The app calculates each person's estimated or verified payable amount and checks whether the entered food total matches the subtotal derived from the bill.

The application runs in the browser and does not require an account or a backend server.

## Features and Functionality

- **Bill and tax configuration:** Enter the final restaurant bill amount, configure CGST and SGST independently, and add restaurant round-off.
- **Flexible tax input:** Set each tax as either a percentage or a fixed rupee amount.
- **Food item catalogue:** Add dishes manually or choose suggestions from the included `foods.json` catalogue.
- **Unit or total dish pricing:** Enter either a unit price multiplied by quantity or the total price for the dish.
- **Multiple diners:** Add people, edit their names, or remove them.
- **Portion allocation:** Assign quantities of each dish to individual diners.
- **Quick equal allocation:** Use **Select All Equally** to divide an item's quantity evenly among the listed diners, or clear its allocation and enter portions manually.
- **Live validation:** See whether the entered food total matches the food subtotal calculated from the restaurant bill, taxes, and round-off.
- **Individual breakdowns:** View each person's food share, CGST, SGST, restaurant round-off share, and payable amount.
- **Rounding reconciliation:** Shows the adjustment needed to reconcile the sum of individually rounded payables with the final restaurant bill.
- **Export and sharing:** Copy the full breakdown, download a TXT summary, or print/save the summary as a PDF.
- **Responsive layout:** Includes a mobile-friendly workflow navigation and layouts for smaller screens.
- **Reset:** Clear the current bill and start over with **Reset All**.

## How to Use the Bill Splitter

Work through the four workflow sections in order.

### 1. Enter Bill Details

1. Enter the **Total Bill Amount** exactly as printed on the restaurant receipt.
2. Set the **CGST** and **SGST** values.
3. For each tax, choose whether the value is a percentage or a fixed amount in rupees.
4. Enter the restaurant's **Round Off** amount. Use `0.00` if there is no round-off.
5. Check the displayed food subtotal. The app derives it from the bill amount after accounting for taxes and round-off.

### 2. Add Food Items

1. Enter a dish name. Start typing to see suggestions from the food catalogue.
2. Choose the price mode:
   - **Total Dish Price:** enter the total price for the dish entry.
   - **Unit Price:** enter the price per unit; the app multiplies it by the quantity.
3. Enter the price and quantity, then select **Add Item**.
4. Repeat for every dish on the receipt.
5. Review the food item table and its total. You can remove an item using the delete control in its row.

The entered food amount should match the food subtotal shown in **Bill Details**. The live verification area indicates whether the amounts match.

### 3. Add People and Allocate Portions

1. Enter a diner's name and select **Add Person**.
2. Repeat until everyone sharing the bill has been added.
3. For each food item, enter the quantity consumed by each person.
4. Use **Select All Equally** to split an item's quantity evenly among all listed diners, or use **Clear** to remove that item's allocations.
5. Check the allocation status for each dish. For a complete split, the assigned quantities must add up to that dish's total quantity without exceeding it.

You can edit or remove a diner using the controls beside their name. Removing a diner also removes their saved portion allocations.

### 4. Review and Export the Split

1. Open **Split Breakdown Result** to see each person's item shares and payable amount.
2. Review the restaurant bill breakdown and food allocation comparison.
3. Check the validation status. A result is marked **Verified** when the bill details are valid, the entered food total matches the derived food subtotal, and all item quantities are fully and correctly allocated. Otherwise, the payable amounts are shown as estimates.
4. Use **Copy Full Breakdown Summary** to copy the result.
5. Use **Export Summary** to choose:
   - **PDF + TXT** — opens the print dialog for a PDF and downloads a TXT summary.
   - **PDF only** — opens the print dialog; choose **Save as PDF** in your browser's print options.
   - **TXT only** — downloads a text summary.

If the PDF print window does not open, allow pop-ups for the site and try again.

### Start a New Bill

Select **Reset All** in the top-right corner and confirm. This clears the current bill details, food items, diners, and allocations.

## Technologies Used

- **HTML5** — page structure and form elements.
- **CSS3** — custom responsive styling.
- **JavaScript (Vanilla JS)** — bill calculations, allocation logic, validation, and export actions.
- **Tailwind CSS (CDN)** — utility-based styling.
- **Lucide Icons (CDN)** — interface icons.
- **JSON** — food item suggestions loaded from `foods.json`.

No build step, package installation, database, or backend is required.

## How to Run Locally

### Option 1: Python

1. Download or clone this repository.
2. Open a terminal in the project folder (the folder containing `index.html`).
3. Run:

   ```bash
   python -m http.server 8000
   ```

4. Open [http://localhost:8000](http://localhost:8000) in your browser.

### Option 2: Visual Studio Code

1. Open the project folder in Visual Studio Code.
2. Install the **Live Server** extension if it is not already installed.
3. Right-click `index.html` and choose **Open with Live Server**.

Opening the site through a local server is recommended because the app loads `foods.json` using `fetch()`.

## Project Structure

```text
BillSplitter/
├── index.html    # Main page and bill-splitting interface
├── styles.css    # Custom styling and responsive layout
├── script.js     # Bill calculations, validation, allocations, and exports
├── foods.json    # Food item suggestions used by autocomplete
└── README.md     # Project documentation
```

## Credits

ChatGPT was used to help plan, develop, and refine the project.

## License

This project is licensed under the **MIT License**.
