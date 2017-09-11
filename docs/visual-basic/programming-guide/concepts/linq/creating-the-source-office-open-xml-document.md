---
title: Creazione del documento di origine Office Open XML (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 23511c4f083dca41c7d1b1302d11dc8b75f974cb
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a><span data-ttu-id="e0c9a-102">Creazione del documento di origine Office Open XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0c9a-102">Creating the Source Office Open XML Document (Visual Basic)</span></span>
<span data-ttu-id="e0c9a-103">In questo argomento viene illustrato come creare il documento WordprocessingML di Office Open XML usato in altri esempi di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="e0c9a-104">Seguendo queste istruzioni, l'output ottenuto sarà uguale a quello indicato in ogni esempio.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-104">If you follow these instructions, your output will match the output provided in each example.</span></span>  
  
 <span data-ttu-id="e0c9a-105">Tuttavia, gli esempi presentati in questa esercitazione funzioneranno con qualsiasi documento WordprocessingML valido.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>  
  
 <span data-ttu-id="e0c9a-106">Per creare il documento usato in questa esercitazione, è necessario selezionare Microsoft Office 2007 o versione successiva oppure è necessario Microsoft Office 2003 con Microsoft Office Compatibility Pack per Word, Excel e formati di File di PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="e0c9a-107">Creazione del documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="e0c9a-107">Creating the WordprocessingML Document</span></span>  
  
#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="e0c9a-108">Per creare il documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="e0c9a-108">To create the WordprocessingML document</span></span>  
  
1.  <span data-ttu-id="e0c9a-109">Creare un nuovo documento di Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-109">Create a new Microsoft Word document.</span></span>  
  
2.  <span data-ttu-id="e0c9a-110">Incollare il testo seguente nel nuovo documento:</span><span class="sxs-lookup"><span data-stu-id="e0c9a-110">Paste the following text into the new document:</span></span>  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3.  <span data-ttu-id="e0c9a-111">Formattare la prima riga con lo stile "Intestazione 1".</span><span class="sxs-lookup"><span data-stu-id="e0c9a-111">Format the first line with the style "Heading 1".</span></span>  
  
4.  <span data-ttu-id="e0c9a-112">Selezionare le righe che contengono il codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-112">Select the lines that contain the Visual Basic code.</span></span> <span data-ttu-id="e0c9a-113">La prima riga inizia con la parola chiave `Imports`.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-113">The first line starts with the `Imports` keyword.</span></span> <span data-ttu-id="e0c9a-114">L'ultima riga è "End Class".</span><span class="sxs-lookup"><span data-stu-id="e0c9a-114">The last line is "End Class".</span></span> <span data-ttu-id="e0c9a-115">Formattare le righe con il tipo di carattere Courier.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-115">Format the lines with the courier font.</span></span> <span data-ttu-id="e0c9a-116">Formattarle con un nuovo stile, da denominare "Code".</span><span class="sxs-lookup"><span data-stu-id="e0c9a-116">Format them with a new style, and name the new style "Code".</span></span>  
  
5.  <span data-ttu-id="e0c9a-117">Infine, selezionare l'intera riga che contiene l'output e formattarla con lo stile `Code`.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>  
  
6.  <span data-ttu-id="e0c9a-118">Salvare il documento e denominarlo SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-118">Save the document, and name it SampleDoc.docx.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0c9a-119">Se si utilizza Microsoft Word 2003, selezionare **documento di Word 2007** nel **Salva come tipo** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c9a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0c9a-120">See Also</span></span>  
 [<span data-ttu-id="e0c9a-121">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0c9a-121">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
