---
title: 'Procedura: recuperare il contenuto della directory Documenti in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: afe236c4b9245ac256fbcbf6bf453de5d706b80f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="f56ce-102">Procedura: recuperare il contenuto della directory Documenti in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f56ce-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="f56ce-103">L'oggetto <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> può essere usato per leggere il contenuto di molte delle directory di **Tutti gli utenti**, ad esempio **Documenti** o **Desktop**.</span><span class="sxs-lookup"><span data-stu-id="f56ce-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="f56ce-104">Per leggere il contenuto dalla cartella Documenti</span><span class="sxs-lookup"><span data-stu-id="f56ce-104">To read from the My Documents folder</span></span>  
  
-   <span data-ttu-id="f56ce-105">Usare il metodo `ReadAllText` per leggere il testo di ogni file in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="f56ce-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="f56ce-106">Il codice seguente consente di specificare una directory e un file e di usare `ReadAllText` per leggere il contenuto nella stringa denominata `patients`.</span><span class="sxs-lookup"><span data-stu-id="f56ce-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     <span data-ttu-id="f56ce-107">[!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f56ce-107">[!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f56ce-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f56ce-108">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>

