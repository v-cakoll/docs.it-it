---
title: "Procedura: Acquisire l'Input dell'utente da un elemento PrintDialog in fase di esecuzione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: a15563560615f5b857220c0b548fc57f31ee4e09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527666"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="f86a3-102">Procedura: Acquisire l'Input dell'utente da un elemento PrintDialog in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f86a3-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="f86a3-103">Mentre è possibile impostare le opzioni relative alla stampa in fase di progettazione, talvolta si desidera modificare queste opzioni in fase di esecuzione, probabilmente a causa di scelte effettuate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f86a3-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="f86a3-104">È possibile acquisire l'input dell'utente per la stampa di un documento usando il <xref:System.Windows.Forms.PrintDialog> e il <xref:System.Drawing.Printing.PrintDocument> componenti.</span><span class="sxs-lookup"><span data-stu-id="f86a3-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="f86a3-105">Per modificare le opzioni di stampa a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f86a3-105">To change print options programmatically</span></span>  
  
1.  <span data-ttu-id="f86a3-106">Aggiungere un <xref:System.Windows.Forms.PrintDialog> e un <xref:System.Drawing.Printing.PrintDocument> al form.</span><span class="sxs-lookup"><span data-stu-id="f86a3-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="f86a3-107">Impostare il <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà del <xref:System.Windows.Forms.PrintDialog> per il <xref:System.Drawing.Printing.PrintDocument> aggiunto al form.</span><span class="sxs-lookup"><span data-stu-id="f86a3-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  <span data-ttu-id="f86a3-108">Visualizzare il <xref:System.Windows.Forms.PrintDialog> componente usando la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f86a3-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  <span data-ttu-id="f86a3-109">Le scelte dell'utente stampa nella finestra di dialogo verranno copiate il <xref:System.Drawing.Printing.PrinterSettings> proprietà del <xref:System.Drawing.Printing.PrintDocument> componente.</span><span class="sxs-lookup"><span data-stu-id="f86a3-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86a3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f86a3-110">See also</span></span>
- [<span data-ttu-id="f86a3-111">Procedura: Stampare un File di testo con più pagine in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f86a3-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="f86a3-112">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f86a3-112">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
