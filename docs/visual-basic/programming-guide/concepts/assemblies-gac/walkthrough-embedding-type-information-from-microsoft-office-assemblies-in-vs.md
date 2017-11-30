---
title: 'Procedura dettagliata: Incorporamento di informazioni sui tipi da assembly di Microsoft Office in Visual Studio (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26e6fee5147e8477c64f7eaf0dc2aeb928c13e15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="f02e0-102">Procedura dettagliata: Incorporamento di informazioni sui tipi da assembly di Microsoft Office in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f02e0-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="f02e0-103">Se si incorporano informazioni sui tipi in un'applicazione che fa riferimento a oggetti COM, è possibile eliminare la necessità di un assembly di interoperabilità primario (PIA).</span><span class="sxs-lookup"><span data-stu-id="f02e0-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="f02e0-104">Inoltre, le informazioni sui tipi incorporate consentono di ottenere l'indipendenza dalla versione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f02e0-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="f02e0-105">Ovvero, il programma può essere scritto in modo da usare tipi di più versioni di una libreria COM senza richiedere un assembly di interoperabilità primario specifico per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="f02e0-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="f02e0-106">Si tratta di uno scenario comune per le applicazioni che usano gli oggetti delle librerie di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="f02e0-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="f02e0-107">L'incorporamento di informazioni sui tipi consente l'uso della stessa build di un programma con delle diverse versioni di Microsoft Office in computer diversi senza dover ridistribuire il programma o l'assembly di interoperabilità primario per ogni versione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="f02e0-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="f02e0-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f02e0-108">Prerequisites</span></span>  
 <span data-ttu-id="f02e0-109">Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="f02e0-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="f02e0-110">Un computer in cui sono installati Visual Studio e Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="f02e0-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="f02e0-111">Un secondo computer in cui sono installati .NET Framework 4 o versione successiva e una versione diversa di Excel.</span><span class="sxs-lookup"><span data-stu-id="f02e0-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <span data-ttu-id="f02e0-112"><a name="BKMK_createapp"></a> Per creare un'applicazione che funziona con più versioni di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="f02e0-112"><a name="BKMK_createapp"></a> To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="f02e0-113">Avviare Visual Studio in un computer in cui è installato Excel.</span><span class="sxs-lookup"><span data-stu-id="f02e0-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="f02e0-114">Nel menu **File** , scegliere **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="f02e0-115">Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="f02e0-116">Selezionare **Applicazione console** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="f02e0-117">Nella casella **Nome** immettere `CreateExcelWorkbook`, quindi scegliere il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="f02e0-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="f02e0-118">Il nuovo progetto viene creato.</span><span class="sxs-lookup"><span data-stu-id="f02e0-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="f02e0-119">Aprire il menu di scelta rapida per il progetto CreateExcelWorkbook e quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-119">Open the shortcut menu for the CreateExcelWorkbook project and then choose **Properties**.</span></span> <span data-ttu-id="f02e0-120">Scegliere il **riferimenti** scheda. Scegliere il pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="f02e0-120">Choose the **References** tab. Choose the **Add** button.</span></span>  
  
5.  <span data-ttu-id="f02e0-121">Nella scheda **.NET** scegliere la versione più recente di `Microsoft.Office.Interop.Excel`.</span><span class="sxs-lookup"><span data-stu-id="f02e0-121">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="f02e0-122">Ad esempio, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-122">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="f02e0-123">Fare clic sul pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="f02e0-123">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="f02e0-124">Nell'elenco di riferimenti per il progetto **CreateExcelWorkbook** selezionare il riferimento per `Microsoft.Office.Interop.Excel` aggiunto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="f02e0-124">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="f02e0-125">Nella finestra **Proprietà** verificare che la proprietà `Embed Interop Types` sia impostata su `True`.</span><span class="sxs-lookup"><span data-stu-id="f02e0-125">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f02e0-126">L'applicazione creata in questa procedura dettagliata viene eseguita con diverse versioni di Microsoft Office grazie alle informazioni incorporate sul tipo di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="f02e0-126">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="f02e0-127">Se la proprietà `Embed Interop Types` è impostata su `False`, è necessario includere un assembly di interoperabilità primario per ogni versione di Microsoft Office con cui verrà eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f02e0-127">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="f02e0-128">Aprire il file Module1. vb.</span><span class="sxs-lookup"><span data-stu-id="f02e0-128">Open the Module1.vb file.</span></span> <span data-ttu-id="f02e0-129">Sostituire il codice nel file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f02e0-129">Replace the code in the file with the following code:</span></span>  
  
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
  
8.  <span data-ttu-id="f02e0-130">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="f02e0-130">Save the project.</span></span>  
  
9. <span data-ttu-id="f02e0-131">Premere CTRL+F5 per compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="f02e0-131">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="f02e0-132">Verificare che sia stata creata una cartella di lavoro di Excel nel percorso specificato nel codice di esempio: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="f02e0-132">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <span data-ttu-id="f02e0-133"><a name="BKMK_publishapp"></a> Per pubblicare l'applicazione in un computer in cui è installata una versione diversa di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="f02e0-133"><a name="BKMK_publishapp"></a> To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="f02e0-134">Aprire il progetto creato da questa procedura dettagliata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f02e0-134">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f02e0-135">Scegliere **Pubblica CreateExcelWorkbook** nel menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-135">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="f02e0-136">Seguire i passaggi della pubblicazione guidata per creare una versione installabile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f02e0-136">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="f02e0-137">Per altre informazioni, vedere [Pubblicazione guidata (sviluppo per Office in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span><span class="sxs-lookup"><span data-stu-id="f02e0-137">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="f02e0-138">Installare l'applicazione in un computer in cui sono installati .NET Framework 4 o versione successiva e una versione diversa di Excel.</span><span class="sxs-lookup"><span data-stu-id="f02e0-138">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="f02e0-139">Al termine dell'installazione eseguire il programma installato.</span><span class="sxs-lookup"><span data-stu-id="f02e0-139">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="f02e0-140">Verificare che sia stata creata una cartella di lavoro di Excel nel percorso specificato nel codice di esempio: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="f02e0-140">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02e0-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f02e0-141">See Also</span></span>  
 [<span data-ttu-id="f02e0-142">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f02e0-142">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
 [<span data-ttu-id="f02e0-143">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f02e0-143">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)
