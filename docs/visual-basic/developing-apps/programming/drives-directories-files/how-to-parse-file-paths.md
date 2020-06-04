---
title: 'Procedura: Analizzare percorsi di file'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
ms.openlocfilehash: eb7714a8594c0bce344eb2e48ebc5053dc3bfbb4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359942"
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="77bdd-102">Procedura: analizzare percorsi di file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77bdd-102">How to: Parse File Paths in Visual Basic</span></span>

<span data-ttu-id="77bdd-103">L'oggetto <xref:Microsoft.VisualBasic.FileIO.FileSystem> offre una serie di metodi utili per l'analisi dei percorsi di file.</span><span class="sxs-lookup"><span data-stu-id="77bdd-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
- <span data-ttu-id="77bdd-104">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> accetta due percorsi e restituisce un percorso combinato correttamente formattato.</span><span class="sxs-lookup"><span data-stu-id="77bdd-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
- <span data-ttu-id="77bdd-105">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> restituisce il percorso assoluto dell'elemento padre del percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="77bdd-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
- <span data-ttu-id="77bdd-106">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> restituisce un oggetto <xref:System.IO.FileInfo> su cui è possibile eseguire query per determinare le proprietà del file, ad esempio il nome e il percorso.</span><span class="sxs-lookup"><span data-stu-id="77bdd-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="77bdd-107">Non basarsi sull'estensione del nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="77bdd-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="77bdd-108">È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77bdd-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="77bdd-109">Per determinare il nome e il percorso di un file</span><span class="sxs-lookup"><span data-stu-id="77bdd-109">To determine a file's name and path</span></span>  
  
- <span data-ttu-id="77bdd-110">Usare le proprietà <xref:System.IO.FileInfo.DirectoryName%2A> e <xref:System.IO.FileInfo.Name%2A> dell'oggetto <xref:System.IO.FileInfo> per determinare il nome e il percorso di un file.</span><span class="sxs-lookup"><span data-stu-id="77bdd-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="77bdd-111">In questo esempio il nome e il percorso vengono determinati e quindi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="77bdd-111">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#54)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="77bdd-112">Per combinare il nome e la directory di un file per creare il percorso completo</span><span class="sxs-lookup"><span data-stu-id="77bdd-112">To combine a file's name and directory to create the full path</span></span>  
  
- <span data-ttu-id="77bdd-113">Usare il metodo `CombinePath` , specificando la directory e il nome.</span><span class="sxs-lookup"><span data-stu-id="77bdd-113">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="77bdd-114">In questo esempio vengono combinate le stringhe `folderPath` e `fileName` create nell'esempio precedente e viene visualizzato il risultato.</span><span class="sxs-lookup"><span data-stu-id="77bdd-114">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="77bdd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77bdd-115">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>
- <xref:System.IO.FileInfo>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>
- [<span data-ttu-id="77bdd-116">Procedura: Ottenere la raccolta di file di una directory</span><span class="sxs-lookup"><span data-stu-id="77bdd-116">How to: Get the Collection of Files in a Directory</span></span>](how-to-get-the-collection-of-files-in-a-directory.md)
