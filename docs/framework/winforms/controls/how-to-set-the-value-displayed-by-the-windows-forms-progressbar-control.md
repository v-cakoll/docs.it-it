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
ms.openlocfilehash: 79ce1e576652d00b323d31dfc6551e168ea0a9a0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743808"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Procedura: impostare il valore visualizzato da un controllo ProgressBar Windows Form
> [!IMPORTANT]
> Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il .NET Framework offre diversi modi per visualizzare un determinato valore all'interno del controllo <xref:System.Windows.Forms.ProgressBar>. L'approccio scelto dipenderà dall'attività a disposizione o dal problema che si sta risolvendo. La tabella seguente illustra gli approcci che è possibile scegliere.  
  
|Approccio|Descrizione|  
|--------------|-----------------|  
|Impostare direttamente il valore del controllo <xref:System.Windows.Forms.ProgressBar>.|Questo approccio è utile per le attività in cui si conosce il totale dell'elemento misurato, ad esempio la lettura di record da un'origine dati. Inoltre, se è necessario impostare il valore solo una volta o due volte, questo è un modo semplice per eseguire questa operazione. Usare infine questo processo se è necessario ridurre il valore visualizzato dall'indicatore di stato.|  
|Aumentare la visualizzazione <xref:System.Windows.Forms.ProgressBar> in base a un valore fisso.|Questo approccio è utile quando si visualizza un conteggio semplice tra il valore minimo e massimo, ad esempio il tempo trascorso o il numero di file elaborati da un totale noto.|  
|Aumentare la visualizzazione del <xref:System.Windows.Forms.ProgressBar> in base a un valore che varia.|Questo approccio è utile quando è necessario modificare il valore visualizzato per un numero di volte in importi diversi. Un esempio mostra la quantità di spazio su disco rigido utilizzata durante la scrittura di una serie di file sul disco.|  
  
 Il modo più diretto per impostare il valore visualizzato da un indicatore di stato consiste nell'impostare la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A>. Questa operazione può essere eseguita in fase di progettazione o in fase di esecuzione.  
  
### <a name="to-set-the-progressbar-value-directly"></a>Per impostare direttamente il valore ProgressBar  
  
1. Impostare i valori di <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> del controllo <xref:System.Windows.Forms.ProgressBar>.  
  
2. Nel codice impostare la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A> del controllo su un valore intero compreso tra i valori minimo e massimo stabiliti.  
  
    > [!NOTE]
    > Se si imposta la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A> al di fuori dei limiti stabiliti dalle proprietà <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A>, il controllo genera un'eccezione <xref:System.ArgumentException>.  
  
     Nell'esempio di codice riportato di seguito viene illustrato come impostare direttamente il valore <xref:System.Windows.Forms.ProgressBar>. Il codice legge i record da un'origine dati e aggiorna l'indicatore di stato e l'etichetta ogni volta che viene letto un record di dati. Questo esempio richiede che il form disponga di un controllo <xref:System.Windows.Forms.Label>, di un controllo <xref:System.Windows.Forms.ProgressBar> e di una tabella di dati con una riga denominata `CustomerRow` con i campi `FirstName` e `LastName`.  
  
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
  
     Se si visualizza lo stato di avanzamento che procede da un intervallo fisso, è possibile impostare il valore e quindi chiamare un metodo che aumenta il valore del controllo <xref:System.Windows.Forms.ProgressBar> in base a tale intervallo. Questa operazione è utile per i timer e per altri scenari in cui non si sta misurando lo stato di avanzamento come percentuale dell'intero.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>Per aumentare l'indicatore di stato in base a un valore fisso  
  
1. Impostare i valori di <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> del controllo <xref:System.Windows.Forms.ProgressBar>.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.ProgressBar.Step%2A> del controllo su un intero che rappresenta la quantità per aumentare il valore visualizzato dell'indicatore di stato.  
  
3. Chiamare il metodo <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> per modificare il valore visualizzato dal set di quantità nella proprietà <xref:System.Windows.Forms.ProgressBar.Step%2A>.  
  
     Nell'esempio di codice seguente viene illustrato come un indicatore di stato può mantenere un conteggio dei file in un'operazione di copia.  
  
     Nell'esempio seguente, quando ogni file viene letto in memoria, l'indicatore di stato e l'etichetta vengono aggiornati per riflettere il totale dei file letti. Questo esempio richiede che il form disponga di un controllo <xref:System.Windows.Forms.Label> e di un controllo <xref:System.Windows.Forms.ProgressBar>.  
  
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
  
     Infine, è possibile aumentare il valore visualizzato da un indicatore di stato in modo che ogni incremento sia un importo univoco. Questa operazione è utile quando si tiene traccia di una serie di operazioni univoche, ad esempio la scrittura di file di dimensioni diverse in un disco rigido o la misurazione dello stato di avanzamento come percentuale dell'intero.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>Per aumentare l'indicatore di stato in base a un valore dinamico  
  
1. Impostare i valori di <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> del controllo <xref:System.Windows.Forms.ProgressBar>.  
  
2. Chiamare il metodo <xref:System.Windows.Forms.ProgressBar.Increment%2A> per modificare il valore visualizzato da un numero intero specificato.  
  
     Nell'esempio di codice seguente viene illustrato come un indicatore di stato può calcolare la quantità di spazio su disco utilizzata durante un'operazione di copia.  
  
     Nell'esempio seguente, quando ogni file viene scritto sul disco rigido, l'indicatore di stato e l'etichetta vengono aggiornati per riflettere la quantità di spazio disponibile su disco rigido. Questo esempio richiede che il form disponga di un controllo <xref:System.Windows.Forms.Label> e di un controllo <xref:System.Windows.Forms.ProgressBar>.  
  
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
