---
title: 'Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office in Visual Studio (C#)'
ms.date: 07/20/2015
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
ms.openlocfilehash: 381173eedc209930e011dfa7f1711167f16d5ef6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187968"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a><span data-ttu-id="0548f-102">Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="0548f-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="0548f-103">Se si incorporano informazioni sui tipi in un'applicazione che fa riferimento a oggetti COM, è possibile eliminare la necessità di un assembly di interoperabilità primario (PIA).</span><span class="sxs-lookup"><span data-stu-id="0548f-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="0548f-104">Inoltre, le informazioni sui tipi incorporate consentono di ottenere l'indipendenza dalla versione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0548f-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="0548f-105">Ovvero, il programma può essere scritto in modo da usare tipi di più versioni di una libreria COM senza richiedere un assembly di interoperabilità primario specifico per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="0548f-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="0548f-106">Si tratta di uno scenario comune per le applicazioni che usano gli oggetti delle librerie di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="0548f-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="0548f-107">L'incorporamento di informazioni sui tipi consente l'uso della stessa build di un programma con delle diverse versioni di Microsoft Office in computer diversi senza dover ridistribuire il programma o l'assembly di interoperabilità primario per ogni versione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="0548f-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="0548f-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0548f-108">Prerequisites</span></span>  
 <span data-ttu-id="0548f-109">Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="0548f-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="0548f-110">Un computer in cui sono installati Visual Studio e Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="0548f-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="0548f-111">Un secondo computer in cui sono installati .NET Framework 4 o versione successiva e una versione diversa di Excel.</span><span class="sxs-lookup"><span data-stu-id="0548f-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <a name="BKMK_createapp"></a> <span data-ttu-id="0548f-112">Per creare un'applicazione che funziona con più versioni di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="0548f-112">To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="0548f-113">Avviare Visual Studio in un computer in cui è installato Excel.</span><span class="sxs-lookup"><span data-stu-id="0548f-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="0548f-114">Nel menu **File** , scegliere **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="0548f-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="0548f-115">Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="0548f-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="0548f-116">Selezionare **Applicazione console** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="0548f-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="0548f-117">Nella casella **Nome** immettere `CreateExcelWorkbook`, quindi scegliere il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="0548f-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="0548f-118">Il nuovo progetto viene creato.</span><span class="sxs-lookup"><span data-stu-id="0548f-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="0548f-119">In **Esplora soluzioni** aprire il menu di scelta rapida per la cartella **Riferimenti**e quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="0548f-119">In **Solution Explorer**, open the shortcut menu for the **References** folder and then choose **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="0548f-120">Nella scheda **.NET** scegliere la versione più recente di `Microsoft.Office.Interop.Excel`.</span><span class="sxs-lookup"><span data-stu-id="0548f-120">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="0548f-121">Ad esempio, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="0548f-121">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="0548f-122">Fare clic sul pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="0548f-122">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="0548f-123">Nell'elenco di riferimenti per il progetto **CreateExcelWorkbook** selezionare il riferimento per `Microsoft.Office.Interop.Excel` aggiunto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="0548f-123">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="0548f-124">Nella finestra **Proprietà** verificare che la proprietà `Embed Interop Types` sia impostata su `True`.</span><span class="sxs-lookup"><span data-stu-id="0548f-124">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0548f-125">L'applicazione creata in questa procedura dettagliata viene eseguita con diverse versioni di Microsoft Office grazie alle informazioni incorporate sul tipo di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="0548f-125">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="0548f-126">Se la proprietà `Embed Interop Types` è impostata su `False`, è necessario includere un assembly di interoperabilità primario per ogni versione di Microsoft Office con cui verrà eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0548f-126">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="0548f-127">Aprire il file **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="0548f-127">Open the **Program.cs** file.</span></span> <span data-ttu-id="0548f-128">Sostituire il codice nel file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0548f-128">Replace the code in the file with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.IO;  
    using Excel = Microsoft.Office.Interop.Excel;  
  
    namespace CreateExcelWorkbook  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                int[] values = {4, 6, 18, 2, 1, 76, 0, 3, 11};  
  
                CreateWorkbook(values, @"C:\SampleFolder\SampleWorkbook.xls");  
            }  
  
            static void CreateWorkbook(int[] values, string filePath)  
            {  
                Excel.Application excelApp = null;  
                Excel.Workbook wkbk;  
                Excel.Worksheet sheet;  
  
                try  
                {  
                        // Start Excel and create a workbook and worksheet.  
                        excelApp = new Excel.Application();  
                        wkbk = excelApp.Workbooks.Add();  
                        sheet = wkbk.Sheets.Add() as Excel.Worksheet;  
                        sheet.Name = "Sample Worksheet";  
  
                        // Write a column of values.  
                        // In the For loop, both the row index and array index start at 1.  
                        // Therefore the value of 4 at array index 0 is not included.  
                        for (int i = 1; i < values.Length; i++)  
                        {  
                            sheet.Cells[i, 1] = values[i];  
                        }  
  
                        // Suppress any alerts and save the file. Create the directory   
                        // if it does not exist. Overwrite the file if it exists.  
                        excelApp.DisplayAlerts = false;  
                        string folderPath = Path.GetDirectoryName(filePath);  
                        if (!Directory.Exists(folderPath))  
                        {  
                            Directory.CreateDirectory(folderPath);  
                        }  
                        wkbk.SaveAs(filePath);  
                }  
                catch  
                {  
                }  
                finally  
                {  
                    sheet = null;  
                    wkbk = null;  
  
                    // Close Excel.  
                    excelApp.Quit();  
                    excelApp = null;  
                }  
            }  
        }  
    }  
    ```  
  
8.  <span data-ttu-id="0548f-129">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="0548f-129">Save the project.</span></span>  
  
9. <span data-ttu-id="0548f-130">Premere CTRL+F5 per compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="0548f-130">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="0548f-131">Verificare che sia stata creata una cartella di lavoro di Excel nel percorso specificato nel codice di esempio: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="0548f-131">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <a name="BKMK_publishapp"></a> <span data-ttu-id="0548f-132">Per pubblicare l'applicazione in un computer in cui è installata una versione diversa di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="0548f-132">To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="0548f-133">Aprire il progetto creato da questa procedura dettagliata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0548f-133">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="0548f-134">Scegliere **Pubblica CreateExcelWorkbook** nel menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="0548f-134">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="0548f-135">Seguire i passaggi della pubblicazione guidata per creare una versione installabile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0548f-135">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="0548f-136">Per altre informazioni, vedere [Pubblicazione guidata (sviluppo per Office in Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0548f-136">For more information, see [Publish Wizard (Office Development in Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).</span></span>  
  
3.  <span data-ttu-id="0548f-137">Installare l'applicazione in un computer in cui sono installati .NET Framework 4 o versione successiva e una versione diversa di Excel.</span><span class="sxs-lookup"><span data-stu-id="0548f-137">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="0548f-138">Al termine dell'installazione eseguire il programma installato.</span><span class="sxs-lookup"><span data-stu-id="0548f-138">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="0548f-139">Verificare che sia stata creata una cartella di lavoro di Excel nel percorso specificato nel codice di esempio: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="0548f-139">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0548f-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0548f-140">See Also</span></span>

- [<span data-ttu-id="0548f-141">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="0548f-141">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
- [<span data-ttu-id="0548f-142">/link (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="0548f-142">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)
