---
title: 'Procedura: impostare e restituire date con il controllo DateTimePicker Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], setting in DateTimePicker
- DateTimePicker control [Windows Forms], setting and returning dates
- examples [Windows Forms], DateTimePicker control
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83a95d2c1aa9f1704f143ae9095cb38596d2c1a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="76058-102">Procedura: impostare e restituire date con il controllo DateTimePicker Windows Form</span><span class="sxs-lookup"><span data-stu-id="76058-102">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="76058-103">La data o l'ora selezionata nel controllo <xref:System.Windows.Forms.DateTimePicker> Windows Form è determinata dalla proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A>,</span><span class="sxs-lookup"><span data-stu-id="76058-103">The currently selected date or time in the Windows Forms <xref:System.Windows.Forms.DateTimePicker> control is determined by the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property.</span></span> <span data-ttu-id="76058-104">che può essere impostata sulla proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> prima della visualizzazione del controllo, ad esempio in fase di progettazione o nell'evento <xref:System.Windows.Forms.Form.Load>, per determinare la data che verrà inizialmente selezionata nel controllo.</span><span class="sxs-lookup"><span data-stu-id="76058-104">You can set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property before the control is displayed (for example, at design time or in the form's <xref:System.Windows.Forms.Form.Load> event) to determine which date will be initially selected in the control.</span></span> <span data-ttu-id="76058-105">Per impostazione predefinita, la proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> del controllo è impostata sulla data corrente.</span><span class="sxs-lookup"><span data-stu-id="76058-105">By default, the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> is set to the current date.</span></span> <span data-ttu-id="76058-106">Se la proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> del controllo viene modificata nel codice, il controllo viene automaticamente aggiornato nel form in base alla nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="76058-106">If you change the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> in code, the control is automatically updated on the form to reflect the new setting.</span></span>  
  
 <span data-ttu-id="76058-107">La proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> restituisce come valore una struttura <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="76058-107">The <xref:System.Windows.Forms.DateTimePicker.Value%2A> property returns a <xref:System.DateTime> structure as its value.</span></span> <span data-ttu-id="76058-108">Numerose proprietà della struttura <xref:System.DateTime> restituiscono informazioni specifiche sulla data visualizzata.</span><span class="sxs-lookup"><span data-stu-id="76058-108">There are several properties of the <xref:System.DateTime> structure that return specific information about the displayed date.</span></span> <span data-ttu-id="76058-109">Tali proprietà, tuttavia, possono essere usate solo per la restituzione di un valore, non per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="76058-109">These properties can only be used to return a value; do not use them to set a value.</span></span>  
  
-   <span data-ttu-id="76058-110">Per i valori relativi alla data, le proprietà <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> e <xref:System.DateTime.Year%2A> restituiscono valori Integer per le unità di tempo corrispondenti della data selezionata.</span><span class="sxs-lookup"><span data-stu-id="76058-110">For date values, the <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A>, and <xref:System.DateTime.Year%2A> properties return integer values for those time units of the selected date.</span></span> <span data-ttu-id="76058-111">La proprietà <xref:System.DateTime.DayOfWeek%2A> restituisce un valore che indica il giorno della settimana selezionato. Per un elenco dei valori disponibili, vedere l'enumerazione <xref:System.DayOfWeek>.</span><span class="sxs-lookup"><span data-stu-id="76058-111">The <xref:System.DateTime.DayOfWeek%2A> property returns a value indicating the selected day of the week (possible values are listed in the <xref:System.DayOfWeek> enumeration).</span></span>  
  
-   <span data-ttu-id="76058-112">Per i valori relativi all'ora, le proprietà <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> e <xref:System.DateTime.Millisecond%2A> restituiscono valori Integer per le unità di tempo corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="76058-112">For time values, the <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A>, and <xref:System.DateTime.Millisecond%2A> properties return integer values for those time units.</span></span> <span data-ttu-id="76058-113">Per configurare il controllo per visualizzare i tempi, vedere [procedura: visualizzare l'ora con il controllo DateTimePicker](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).</span><span class="sxs-lookup"><span data-stu-id="76058-113">To configure the control to display times, see [How to: Display Time with the DateTimePicker Control](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).</span></span>  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a><span data-ttu-id="76058-114">Per impostare i valori di data e di ora del controllo</span><span class="sxs-lookup"><span data-stu-id="76058-114">To set the date and time value of the control</span></span>  
  
-   <span data-ttu-id="76058-115">Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> su un valore di data o di ora.</span><span class="sxs-lookup"><span data-stu-id="76058-115">Set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to a date or time value.</span></span>  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a><span data-ttu-id="76058-116">Per restituire il valore di data e di ora</span><span class="sxs-lookup"><span data-stu-id="76058-116">To return the date and time value</span></span>  
  
-   <span data-ttu-id="76058-117">Chiamare la proprietà <xref:System.Windows.Forms.DateTimePicker.Text%2A> per restituire il valore completo nel formato impostato per il controllo, oppure chiamare il metodo appropriato della proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> per restituire una parte del valore.</span><span class="sxs-lookup"><span data-stu-id="76058-117">Call the <xref:System.Windows.Forms.DateTimePicker.Text%2A> property to return the entire value as formatted in the control, or call the appropriate method of the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to return a part of the value.</span></span> <span data-ttu-id="76058-118">Usare <xref:System.Windows.Forms.DateTimePicker.ToString%2A> per convertire le informazioni in una stringa visualizzabile all'utente.</span><span class="sxs-lookup"><span data-stu-id="76058-118">Use <xref:System.Windows.Forms.DateTimePicker.ToString%2A> to convert the information into a string that can be displayed to the user.</span></span>  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",   
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",   
       DateTimePicker1.Value.Millisecond.ToString)  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +   
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +   
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +   
       dateTimePicker1.Value.Millisecond.ToString());  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="76058-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76058-119">See Also</span></span>  
 [<span data-ttu-id="76058-120">Controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="76058-120">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [<span data-ttu-id="76058-121">Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form</span><span class="sxs-lookup"><span data-stu-id="76058-121">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
