---
title: Impostare il valore visualizzato dal controllo ProgressBar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: d295079a96ca19a4e4c98e113a3f3051c6403182
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141811"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="19623-102">Procedura: impostare il valore visualizzato da un controllo ProgressBar Windows Form</span><span class="sxs-lookup"><span data-stu-id="19623-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="19623-103">Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="19623-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="19623-104">.NET Framework offre diversi modi per visualizzare un <xref:System.Windows.Forms.ProgressBar> determinato valore all'interno del controllo.</span><span class="sxs-lookup"><span data-stu-id="19623-104">The .NET Framework gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="19623-105">L'approccio scelto dipenderà dal compito a portata di mano o dal problema che si sta risolvendo.</span><span class="sxs-lookup"><span data-stu-id="19623-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="19623-106">Nella tabella seguente vengono illustrati gli approcci che è possibile scegliere.</span><span class="sxs-lookup"><span data-stu-id="19623-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="19623-107">Approccio</span><span class="sxs-lookup"><span data-stu-id="19623-107">Approach</span></span>|<span data-ttu-id="19623-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19623-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="19623-109">Impostare direttamente <xref:System.Windows.Forms.ProgressBar> il valore del controllo.</span><span class="sxs-lookup"><span data-stu-id="19623-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="19623-110">Questo approccio è utile per le attività in cui si conosce il totale dell'elemento misurato che verrà coinvolto, ad esempio la lettura di record da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="19623-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="19623-111">Inoltre, se è necessario impostare il valore solo una o due volte, questo è un modo semplice per farlo.</span><span class="sxs-lookup"><span data-stu-id="19623-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="19623-112">Infine, utilizzare questo processo se è necessario ridurre il valore visualizzato dall'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="19623-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="19623-113">Aumentare <xref:System.Windows.Forms.ProgressBar> la visualizzazione di un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="19623-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="19623-114">Questo approccio è utile quando si visualizza un conteggio semplice tra il minimo e il massimo, ad esempio il tempo trascorso o il numero di file elaborati da un totale noto.</span><span class="sxs-lookup"><span data-stu-id="19623-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="19623-115">Aumentare <xref:System.Windows.Forms.ProgressBar> la visualizzazione di un valore che varia.</span><span class="sxs-lookup"><span data-stu-id="19623-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="19623-116">Questo approccio è utile quando è necessario modificare il valore visualizzato un numero di volte in quantità diverse.</span><span class="sxs-lookup"><span data-stu-id="19623-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="19623-117">Un esempio potrebbe essere che mostra la quantità di spazio sul disco rigido utilizzato durante la scrittura di una serie di file sul disco.</span><span class="sxs-lookup"><span data-stu-id="19623-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="19623-118">Il modo più diretto per impostare il valore visualizzato <xref:System.Windows.Forms.ProgressBar.Value%2A> da un indicatore di stato consiste nell'impostare la proprietà .</span><span class="sxs-lookup"><span data-stu-id="19623-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="19623-119">Questa operazione può essere eseguita in fase di progettazione o in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="19623-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="19623-120">Per impostare direttamente il valore ProgressBar</span><span class="sxs-lookup"><span data-stu-id="19623-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="19623-121">Impostare <xref:System.Windows.Forms.ProgressBar> i <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valori <xref:System.Windows.Forms.ProgressBar.Maximum%2A> e il controllo.</span><span class="sxs-lookup"><span data-stu-id="19623-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="19623-122">Nel codice impostare la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà del controllo su un valore intero compreso tra i valori minimo e massimo stabiliti.</span><span class="sxs-lookup"><span data-stu-id="19623-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="19623-123">Se si <xref:System.Windows.Forms.ProgressBar.Value%2A> imposta la proprietà all'esterno <xref:System.Windows.Forms.ProgressBar.Maximum%2A> dei limiti stabiliti <xref:System.ArgumentException> dalle proprietà <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e , il controllo genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="19623-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="19623-124">Nell'esempio di codice riportato <xref:System.Windows.Forms.ProgressBar> di seguito viene illustrato come impostare direttamente il valore.</span><span class="sxs-lookup"><span data-stu-id="19623-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="19623-125">Il codice legge i record da un'origine dati e aggiorna l'indicatore di stato e l'etichetta ogni volta che viene letto un record di dati.</span><span class="sxs-lookup"><span data-stu-id="19623-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="19623-126">Questo esempio richiede che <xref:System.Windows.Forms.Label> il form <xref:System.Windows.Forms.ProgressBar> contera un controllo, `CustomerRow` un `FirstName` `LastName` controllo e una tabella dati con una riga denominata con e i campi.</span><span class="sxs-lookup"><span data-stu-id="19623-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     Se si visualizza lo stato di avanzamento che procede di un intervallo fisso, è possibile impostare il valore e quindi chiamare un metodo che aumenta il <xref:System.Windows.Forms.ProgressBar> valore del controllo di tale intervallo. <span data-ttu-id="19623-128">Ciò è utile per i timer e altri scenari in cui non si misura lo stato di avanzamento come percentuale dell'intero.</span><span class="sxs-lookup"><span data-stu-id="19623-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="19623-129">Per aumentare l'indicatore di avanzamento di un valore fisso</span><span class="sxs-lookup"><span data-stu-id="19623-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="19623-130">Impostare <xref:System.Windows.Forms.ProgressBar> i <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valori <xref:System.Windows.Forms.ProgressBar.Maximum%2A> e il controllo.</span><span class="sxs-lookup"><span data-stu-id="19623-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="19623-131">Impostare la <xref:System.Windows.Forms.ProgressBar.Step%2A> proprietà del controllo su un numero intero che rappresenta la quantità per aumentare il valore visualizzato dell'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="19623-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="19623-132">Chiamare <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> il metodo per modificare il valore visualizzato <xref:System.Windows.Forms.ProgressBar.Step%2A> dalla quantità impostata nella proprietà .</span><span class="sxs-lookup"><span data-stu-id="19623-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="19623-133">Esempio di codice seguente viene illustrato come un indicatore di stato può mantenere un conteggio dei file in un'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="19623-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="19623-134">Nell'esempio seguente, quando ogni file viene letto in memoria, l'indicatore di stato e l'etichetta vengono aggiornati per riflettere il totale dei file letti.</span><span class="sxs-lookup"><span data-stu-id="19623-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="19623-135">Per eseguire questo esempio <xref:System.Windows.Forms.Label> è necessario <xref:System.Windows.Forms.ProgressBar> che il form disponga di un controllo e di un controllo.</span><span class="sxs-lookup"><span data-stu-id="19623-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     Infine, è possibile aumentare il valore visualizzato da una barra di avanzamento in modo che ogni aumento sia un importo univoco. <span data-ttu-id="19623-137">Ciò è utile quando si tiene traccia di una serie di operazioni univoche, ad esempio la scrittura di file di dimensioni diverse su un disco rigido o la misurazione dello stato di avanzamento come percentuale dell'intero.</span><span class="sxs-lookup"><span data-stu-id="19623-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="19623-138">Per aumentare l'indicatore di stato di un valore dinamico</span><span class="sxs-lookup"><span data-stu-id="19623-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="19623-139">Impostare <xref:System.Windows.Forms.ProgressBar> i <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valori <xref:System.Windows.Forms.ProgressBar.Maximum%2A> e il controllo.</span><span class="sxs-lookup"><span data-stu-id="19623-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="19623-140">Chiamare <xref:System.Windows.Forms.ProgressBar.Increment%2A> il metodo per modificare il valore visualizzato da un numero intero specificato.</span><span class="sxs-lookup"><span data-stu-id="19623-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="19623-141">Nell'esempio di codice riportato di seguito viene illustrato come un indicatore di stato può calcolare la quantità di spazio su disco utilizzata durante un'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="19623-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="19623-142">Nell'esempio seguente, quando ogni file viene scritto sul disco rigido, l'indicatore di stato e l'etichetta vengono aggiornati per riflettere la quantità di spazio disponibile sul disco rigido.</span><span class="sxs-lookup"><span data-stu-id="19623-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="19623-143">Per eseguire questo esempio <xref:System.Windows.Forms.Label> è necessario <xref:System.Windows.Forms.ProgressBar> che il form disponga di un controllo e di un controllo.</span><span class="sxs-lookup"><span data-stu-id="19623-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="19623-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19623-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="19623-145">Cenni preliminari sul controllo ProgressBar</span><span class="sxs-lookup"><span data-stu-id="19623-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="19623-146">Controllo ProgressBar</span><span class="sxs-lookup"><span data-stu-id="19623-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
