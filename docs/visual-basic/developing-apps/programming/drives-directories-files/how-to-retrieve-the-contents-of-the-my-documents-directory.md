---
title: 'Procedura: Recuperare il contenuto della directory Documenti in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: f03dbe1811dd5367dab2d32d94ba35ff05fad198
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623143"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="ccb3c-102">Procedura: Recuperare il contenuto della directory Documenti in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccb3c-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="ccb3c-103">L'oggetto <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> può essere usato per leggere il contenuto di molte delle directory di **Tutti gli utenti**, ad esempio **Documenti** o **Desktop**.</span><span class="sxs-lookup"><span data-stu-id="ccb3c-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="ccb3c-104">Per leggere il contenuto dalla cartella Documenti</span><span class="sxs-lookup"><span data-stu-id="ccb3c-104">To read from the My Documents folder</span></span>  
  
- <span data-ttu-id="ccb3c-105">Usare il metodo `ReadAllText` per leggere il testo di ogni file in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="ccb3c-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="ccb3c-106">Il codice seguente consente di specificare una directory e un file e di usare `ReadAllText` per leggere il contenuto nella stringa denominata `patients`.</span><span class="sxs-lookup"><span data-stu-id="ccb3c-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="ccb3c-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccb3c-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
