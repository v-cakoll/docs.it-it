---
title: 'Procedura: Impostare il valore visualizzato dal controllo ProgressBar di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 42a9e0f67f00c1a706b72ab0eeb522e99d8a8dfe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300476"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Procedura: Impostare il valore visualizzato dal controllo ProgressBar di Windows Forms
> [!IMPORTANT]
>  Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ti offre diversi modi per visualizzare un determinato valore all'interno di <xref:System.Windows.Forms.ProgressBar> controllo. Il metodo scelto varia in base all'attività in corso o il problema da risolvere. Nella tabella seguente mostra gli approcci che è possibile scegliere.  
  
|Approccio|Descrizione|  
|--------------|-----------------|  
|Impostare il valore della <xref:System.Windows.Forms.ProgressBar> controllare direttamente.|Questo approccio è utile per le attività in cui si conosce il totale dell'elemento misurato che sarà coinvolti, quali la lettura dei record da un'origine dati. Inoltre, se è solo necessario impostare il valore di una o due volte, questo è un modo semplice per eseguire questa operazione. Infine, usare questo processo se è necessario diminuire il valore visualizzato per l'indicatore di stato.|  
|Aumentare il <xref:System.Windows.Forms.ProgressBar> visualizzare da un valore fisso.|Questo approccio è utile quando si visualizzano un semplice conteggio tra i valori minimo e massimo, ad esempio il tempo trascorso o il numero di file che sono stati elaborati su un totale noto.|  
|Aumentare il <xref:System.Windows.Forms.ProgressBar> visualizzare da un valore diverso.|Questo approccio è utile quando è necessario modificare il valore visualizzato un numero di volte in importi diversi. La quantità di spazio su disco utilizzato durante la scrittura di una serie di file su disco viene indicato un esempio.|  
  
 Il modo più diretto per impostare il valore visualizzato da una barra di stato di avanzamento consiste nell'impostare il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà. Questa operazione può essere eseguita in fase di progettazione o in fase di esecuzione.  
  
### <a name="to-set-the-progressbar-value-directly"></a>Per impostare il valore ProgressBar direttamente  
  
1. Impostare il <xref:System.Windows.Forms.ProgressBar> del controllo <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valori.  
  
2. Nel codice, impostare il controllo <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà a valore intero compreso tra i valori minimi e massimo è stato stabilito.  
  
    > [!NOTE]
    >  Se si imposta la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà esterna ai limiti stabiliti dal <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> delle proprietà, il controllo genera un <xref:System.ArgumentException> eccezione.  
  
     Esempio di codice seguente viene illustrato come impostare il <xref:System.Windows.Forms.ProgressBar> valore direttamente. Il codice legge i record da un'origine dati e aggiorna l'indicatore di stato e l'etichetta ogni volta che viene letto un record dei dati. Questo esempio richiede che il form contenga un <xref:System.Windows.Forms.Label> (controllo), una <xref:System.Windows.Forms.ProgressBar> controllo e una tabella dati con una riga chiamata `CustomerRow` con `FirstName` e `LastName` campi.  
  
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
  
     Se viene visualizzato lo stato di avanzamento che consente di passare da un intervallo fisso, è possibile impostare il valore e quindi chiamare un metodo che consentono di aumentare la <xref:System.Windows.Forms.ProgressBar> valore del controllo in base a tale intervallo. Ciò è utile per i timer e altri scenari in cui si sta misurando non lo stato di avanzamento in percentuale rispetto al totale.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>Per aumentare l'indicatore di stato da un valore fisso  
  
1. Impostare il <xref:System.Windows.Forms.ProgressBar> del controllo <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valori.  
  
2. Impostare il controllo <xref:System.Windows.Forms.ProgressBar.Step%2A> proprietà a valore integer che rappresenta la quantità per aumentare l'indicatore di stato valore visualizzato.  
  
3. Chiamare il <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> metodo per modificare il valore visualizzato per il valore impostato il <xref:System.Windows.Forms.ProgressBar.Step%2A> proprietà.  
  
     Esempio di codice seguente viene illustrato come un indicatore di stato può mantenere un conteggio dei file in un'operazione di copia.  
  
     Nell'esempio seguente, perché ogni file viene letto in memoria, l'indicatore di stato e l'etichetta vengono aggiornati per riflettere che i numero totale di file di lettura. Questo esempio richiede che il form contenga un <xref:System.Windows.Forms.Label> controllo e un <xref:System.Windows.Forms.ProgressBar> controllo.  
  
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
  
     Infine, è possibile aumentare il valore visualizzato da un indicatore di stato in modo che ogni incremento è una quantità univoca. Ciò è utile quando si sta tenendo traccia di una serie di operazioni univoche, ad esempio la scrittura di file di dimensioni diverse in un disco rigido o misurare lo stato di avanzamento come percentuale dell'intero.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>Per aumentare l'indicatore di stato di un valore dinamico  
  
1. Impostare il <xref:System.Windows.Forms.ProgressBar> del controllo <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valori.  
  
2. Chiamare il <xref:System.Windows.Forms.ProgressBar.Increment%2A> metodo per modificare il valore visualizzato da un intero specificato.  
  
     Esempio di codice seguente viene illustrato come un indicatore di stato possibile calcolare quanto spazio su disco è stato utilizzato durante un'operazione di copia.  
  
     Nell'esempio seguente, perché ogni file viene scritto sul disco rigido, l'indicatore di stato e l'etichetta vengono aggiornati per riflettere la quantità di spazio su disco disponibile. Questo esempio richiede che il form contenga un <xref:System.Windows.Forms.Label> controllo e un <xref:System.Windows.Forms.ProgressBar> controllo.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [Panoramica sul controllo ProgressBar](progressbar-control-overview-windows-forms.md)
- [Controllo ProgressBar](progressbar-control-windows-forms.md)
