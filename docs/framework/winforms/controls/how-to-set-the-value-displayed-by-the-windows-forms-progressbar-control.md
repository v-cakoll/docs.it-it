---
title: Impostare il valore visualizzato dal controllo ProgressBar
description: Informazioni su come impostare il valore visualizzato dal controllo Windows Forms ProgressBar. Esistono diversi approcci che è possibile scegliere di usare.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 75fe1b416636471d797a39134f45a05c972c9d39
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618103"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="1d73f-104">Procedura: impostare il valore visualizzato da un controllo ProgressBar Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d73f-104">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1d73f-105">Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="1d73f-105">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="1d73f-106">Il .NET Framework offre diversi modi per visualizzare un determinato valore all'interno del <xref:System.Windows.Forms.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="1d73f-106">The .NET Framework gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="1d73f-107">L'approccio scelto dipenderà dall'attività a disposizione o dal problema che si sta risolvendo.</span><span class="sxs-lookup"><span data-stu-id="1d73f-107">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="1d73f-108">La tabella seguente illustra gli approcci che è possibile scegliere.</span><span class="sxs-lookup"><span data-stu-id="1d73f-108">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="1d73f-109">Approccio</span><span class="sxs-lookup"><span data-stu-id="1d73f-109">Approach</span></span>|<span data-ttu-id="1d73f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d73f-110">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1d73f-111">Impostare direttamente il valore del <xref:System.Windows.Forms.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="1d73f-111">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="1d73f-112">Questo approccio è utile per le attività in cui si conosce il totale dell'elemento misurato, ad esempio la lettura di record da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1d73f-112">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="1d73f-113">Inoltre, se è necessario impostare il valore solo una volta o due volte, questo è un modo semplice per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="1d73f-113">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="1d73f-114">Usare infine questo processo se è necessario ridurre il valore visualizzato dall'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="1d73f-114">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="1d73f-115">Aumentare la <xref:System.Windows.Forms.ProgressBar> visualizzazione in base a un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="1d73f-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="1d73f-116">Questo approccio è utile quando si visualizza un conteggio semplice tra il valore minimo e massimo, ad esempio il tempo trascorso o il numero di file elaborati da un totale noto.</span><span class="sxs-lookup"><span data-stu-id="1d73f-116">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="1d73f-117">Aumentare la <xref:System.Windows.Forms.ProgressBar> visualizzazione in base a un valore che varia.</span><span class="sxs-lookup"><span data-stu-id="1d73f-117">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="1d73f-118">Questo approccio è utile quando è necessario modificare il valore visualizzato per un numero di volte in importi diversi.</span><span class="sxs-lookup"><span data-stu-id="1d73f-118">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="1d73f-119">Un esempio mostra la quantità di spazio su disco rigido utilizzata durante la scrittura di una serie di file sul disco.</span><span class="sxs-lookup"><span data-stu-id="1d73f-119">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="1d73f-120">Il modo più diretto per impostare il valore visualizzato da un indicatore di stato consiste nell'impostare la <xref:System.Windows.Forms.ProgressBar.Value%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1d73f-120">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="1d73f-121">Questa operazione può essere eseguita in fase di progettazione o in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1d73f-121">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="1d73f-122">Per impostare direttamente il valore ProgressBar</span><span class="sxs-lookup"><span data-stu-id="1d73f-122">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="1d73f-123">Impostare i <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valori e del controllo <xref:System.Windows.Forms.ProgressBar.Maximum%2A> .</span><span class="sxs-lookup"><span data-stu-id="1d73f-123">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="1d73f-124">Nel codice impostare la proprietà del controllo <xref:System.Windows.Forms.ProgressBar.Value%2A> su un valore intero compreso tra i valori minimo e massimo stabiliti.</span><span class="sxs-lookup"><span data-stu-id="1d73f-124">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1d73f-125">Se si imposta la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà al di fuori dei limiti stabiliti dalle <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> proprietà e, il controllo genera un' <xref:System.ArgumentException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="1d73f-125">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="1d73f-126">Nell'esempio di codice riportato di seguito viene illustrato come impostare <xref:System.Windows.Forms.ProgressBar> direttamente il valore.</span><span class="sxs-lookup"><span data-stu-id="1d73f-126">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="1d73f-127">Il codice legge i record da un'origine dati e aggiorna l'indicatore di stato e l'etichetta ogni volta che viene letto un record di dati.</span><span class="sxs-lookup"><span data-stu-id="1d73f-127">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="1d73f-128">Questo esempio richiede che il form disponga di un <xref:System.Windows.Forms.Label> controllo, di un <xref:System.Windows.Forms.ProgressBar> controllo e di una tabella di dati con una riga denominata `CustomerRow` con i `FirstName` `LastName` campi e.</span><span class="sxs-lookup"><span data-stu-id="1d73f-128">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
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
  
     Se si visualizza lo stato di avanzamento che procede da un intervallo fisso, è possibile impostare il valore e quindi chiamare un metodo che aumenta il <xref:System.Windows.Forms.ProgressBar> valore del controllo in base a tale intervallo. <span data-ttu-id="1d73f-130">Questa operazione è utile per i timer e per altri scenari in cui non si sta misurando lo stato di avanzamento come percentuale dell'intero.</span><span class="sxs-lookup"><span data-stu-id="1d73f-130">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="1d73f-131">Per aumentare l'indicatore di stato in base a un valore fisso</span><span class="sxs-lookup"><span data-stu-id="1d73f-131">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="1d73f-132">Impostare i <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valori e del controllo <xref:System.Windows.Forms.ProgressBar.Maximum%2A> .</span><span class="sxs-lookup"><span data-stu-id="1d73f-132">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="1d73f-133">Impostare la proprietà del controllo <xref:System.Windows.Forms.ProgressBar.Step%2A> su un intero che rappresenta la quantità per aumentare il valore visualizzato dell'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="1d73f-133">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="1d73f-134">Chiamare il <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> metodo per modificare il valore visualizzato dalla quantità impostata nella <xref:System.Windows.Forms.ProgressBar.Step%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1d73f-134">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="1d73f-135">Nell'esempio di codice seguente viene illustrato come un indicatore di stato può mantenere un conteggio dei file in un'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="1d73f-135">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="1d73f-136">Nell'esempio seguente, quando ogni file viene letto in memoria, l'indicatore di stato e l'etichetta vengono aggiornati per riflettere il totale dei file letti.</span><span class="sxs-lookup"><span data-stu-id="1d73f-136">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="1d73f-137">Questo esempio richiede che il form disponga di un <xref:System.Windows.Forms.Label> controllo e di un <xref:System.Windows.Forms.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="1d73f-137">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
     Infine, è possibile aumentare il valore visualizzato da un indicatore di stato in modo che ogni incremento sia un importo univoco. <span data-ttu-id="1d73f-139">Questa operazione è utile quando si tiene traccia di una serie di operazioni univoche, ad esempio la scrittura di file di dimensioni diverse in un disco rigido o la misurazione dello stato di avanzamento come percentuale dell'intero.</span><span class="sxs-lookup"><span data-stu-id="1d73f-139">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="1d73f-140">Per aumentare l'indicatore di stato in base a un valore dinamico</span><span class="sxs-lookup"><span data-stu-id="1d73f-140">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="1d73f-141">Impostare i <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valori e del controllo <xref:System.Windows.Forms.ProgressBar.Maximum%2A> .</span><span class="sxs-lookup"><span data-stu-id="1d73f-141">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="1d73f-142">Chiamare il <xref:System.Windows.Forms.ProgressBar.Increment%2A> metodo per modificare il valore visualizzato da un Integer specificato.</span><span class="sxs-lookup"><span data-stu-id="1d73f-142">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="1d73f-143">Nell'esempio di codice seguente viene illustrato come un indicatore di stato può calcolare la quantità di spazio su disco utilizzata durante un'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="1d73f-143">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="1d73f-144">Nell'esempio seguente, quando ogni file viene scritto sul disco rigido, l'indicatore di stato e l'etichetta vengono aggiornati per riflettere la quantità di spazio disponibile su disco rigido.</span><span class="sxs-lookup"><span data-stu-id="1d73f-144">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="1d73f-145">Questo esempio richiede che il form disponga di un <xref:System.Windows.Forms.Label> controllo e di un <xref:System.Windows.Forms.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="1d73f-145">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d73f-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d73f-146">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="1d73f-147">Cenni preliminari sul controllo ProgressBar</span><span class="sxs-lookup"><span data-stu-id="1d73f-147">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="1d73f-148">Controllo ProgressBar</span><span class="sxs-lookup"><span data-stu-id="1d73f-148">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
