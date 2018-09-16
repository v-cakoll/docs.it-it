---
title: 'Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office in Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
ms.openlocfilehash: bc8f7585964bdd60bac5d5a466f6276fab288c78
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668210"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a>Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office in Visual Studio (Visual Basic)
Se si incorporano informazioni sui tipi in un'applicazione che fa riferimento a oggetti COM, è possibile eliminare la necessità di un assembly di interoperabilità primario (PIA). Inoltre, le informazioni sui tipi incorporate consentono di ottenere l'indipendenza dalla versione per l'applicazione. Ovvero, il programma può essere scritto in modo da usare tipi di più versioni di una libreria COM senza richiedere un assembly di interoperabilità primario specifico per ogni versione. Si tratta di uno scenario comune per le applicazioni che usano gli oggetti delle librerie di Microsoft Office. L'incorporamento di informazioni sui tipi consente l'uso della stessa build di un programma con delle diverse versioni di Microsoft Office in computer diversi senza dover ridistribuire il programma o l'assembly di interoperabilità primario per ogni versione di Microsoft Office.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:  
  
-   Un computer in cui sono installati Visual Studio e Microsoft Excel.  
  
-   Un secondo computer in cui sono installati .NET Framework 4 o versione successiva e una versione diversa di Excel.  
  
##  <a name="BKMK_createapp"></a> Per creare un'applicazione che funziona con più versioni di Microsoft Office  
  
1.  Avviare Visual Studio in un computer in cui è installato Excel.  
  
2.  Nel menu **File** , scegliere **Nuovo**, **Progetto**.  
  
3.  Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**. Selezionare **Applicazione console** nel riquadro **Modelli**. Nella casella **Nome** immettere `CreateExcelWorkbook`, quindi scegliere il pulsante **OK** . Il nuovo progetto viene creato.  
  
4.  Aprire il menu di scelta rapida per il progetto CreateExcelWorkbook, quindi scegliere **proprietà**. Scegliere il **riferimenti** scheda. Scegliere il pulsante **Aggiungi**.  
  
5.  Nella scheda **.NET** scegliere la versione più recente di `Microsoft.Office.Interop.Excel`. Ad esempio, **Microsoft.Office.Interop.Excel 14.0.0.0**. Fare clic sul pulsante **OK** .  
  
6.  Nell'elenco di riferimenti per il progetto **CreateExcelWorkbook** selezionare il riferimento per `Microsoft.Office.Interop.Excel` aggiunto nel passaggio precedente. Nella finestra **Proprietà** verificare che la proprietà `Embed Interop Types` sia impostata su `True`.  
  
    > [!NOTE]
    >  L'applicazione creata in questa procedura dettagliata viene eseguita con diverse versioni di Microsoft Office grazie alle informazioni incorporate sul tipo di interoperabilità. Se la proprietà `Embed Interop Types` è impostata su `False`, è necessario includere un assembly di interoperabilità primario per ogni versione di Microsoft Office con cui verrà eseguita l'applicazione.  
  
7.  Aprire il file Module1.vb. Sostituire il codice nel file con il codice seguente:  
  
    ```vb  
    Imports Excel = Microsoft.Office.Interop.Excel  
  
    Module Module1  
  
        Sub Main()  
            Dim values = {4, 6, 18, 2, 1, 76, 0, 3, 11}  
  
            CreateWorkbook(values, "C:\SampleFolder\SampleWorkbook.xls")  
        End Sub  
  
        Sub CreateWorkbook(ByVal values As Integer(), ByVal filePath As String)  
            Dim excelApp As Excel.Application = Nothing  
            Dim wkbk As Excel.Workbook  
            Dim sheet As Excel.Worksheet  
  
            Try  
                ' Start Excel and create a workbook and worksheet.  
                excelApp = New Excel.Application  
                wkbk = excelApp.Workbooks.Add()  
                sheet = CType(wkbk.Sheets.Add(), Excel.Worksheet)  
                sheet.Name = "Sample Worksheet"  
  
                ' Write a column of values.  
                ' In the For loop, both the row index and array index start at 1.  
                ' Therefore the value of 4 at array index 0 is not included.  
                For i = 1 To values.Length - 1  
                    sheet.Cells(i, 1) = values(i)  
                Next  
  
                ' Suppress any alerts and save the file. Create the directory   
                ' if it does not exist. Overwrite the file if it exists.  
                excelApp.DisplayAlerts = False  
                Dim folderPath = My.Computer.FileSystem.GetParentPath(filePath)  
                If Not My.Computer.FileSystem.DirectoryExists(folderPath) Then  
                    My.Computer.FileSystem.CreateDirectory(folderPath)  
                End If  
                wkbk.SaveAs(filePath)  
        Catch  
  
            Finally  
                sheet = Nothing  
                wkbk = Nothing  
  
                ' Close Excel.  
                excelApp.Quit()  
                excelApp = Nothing  
            End Try  
  
        End Sub  
    End Module  
    ```  
  
8.  Salvare il progetto.  
  
9. Premere CTRL+F5 per compilare ed eseguire il progetto. Verificare che sia stata creata una cartella di lavoro di Excel nel percorso specificato nel codice di esempio: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a> Per pubblicare l'applicazione in un computer in cui è installata una versione diversa di Microsoft Office  
  
1.  Aprire il progetto creato da questa procedura dettagliata in Visual Studio.  
  
2.  Scegliere **Pubblica CreateExcelWorkbook** nel menu **Compila**. Seguire i passaggi della pubblicazione guidata per creare una versione installabile dell'applicazione. Per altre informazioni, vedere [Pubblicazione guidata (sviluppo per Office in Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).  
  
3.  Installare l'applicazione in un computer in cui sono installati .NET Framework 4 o versione successiva e una versione diversa di Excel.  
  
4.  Al termine dell'installazione eseguire il programma installato.  
  
5.  Verificare che sia stata creata una cartella di lavoro di Excel nel percorso specificato nel codice di esempio: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
- [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)
