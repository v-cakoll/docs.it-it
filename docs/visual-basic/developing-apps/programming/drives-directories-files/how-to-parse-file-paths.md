---
title: 'Procedura: analizzare percorsi di file'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
ms.openlocfilehash: 6a959994be3a57795dc9f7e3447fa54bf075d3ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335355"
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="e81fb-102">Procedura: analizzare percorsi di file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e81fb-102">How to: Parse File Paths in Visual Basic</span></span>

<span data-ttu-id="e81fb-103">L'oggetto <xref:Microsoft.VisualBasic.FileIO.FileSystem> offre una serie di metodi utili per l'analisi dei percorsi di file.</span><span class="sxs-lookup"><span data-stu-id="e81fb-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
- <span data-ttu-id="e81fb-104">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> accetta due percorsi e restituisce un percorso combinato correttamente formattato.</span><span class="sxs-lookup"><span data-stu-id="e81fb-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
- <span data-ttu-id="e81fb-105">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> restituisce il percorso assoluto dell'elemento padre del percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="e81fb-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
- <span data-ttu-id="e81fb-106">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> restituisce un oggetto <xref:System.IO.FileInfo> su cui è possibile eseguire query per determinare le proprietà del file, ad esempio il nome e il percorso.</span><span class="sxs-lookup"><span data-stu-id="e81fb-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="e81fb-107">Non basarsi sull'estensione del nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="e81fb-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="e81fb-108">È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e81fb-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="e81fb-109">Per determinare il nome e il percorso di un file</span><span class="sxs-lookup"><span data-stu-id="e81fb-109">To determine a file's name and path</span></span>  
  
- <span data-ttu-id="e81fb-110">Usare le proprietà <xref:System.IO.FileInfo.DirectoryName%2A> e <xref:System.IO.FileInfo.Name%2A> dell'oggetto <xref:System.IO.FileInfo> per determinare il nome e il percorso di un file.</span><span class="sxs-lookup"><span data-stu-id="e81fb-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="e81fb-111">In questo esempio il nome e il percorso vengono determinati e quindi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="e81fb-111">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#54)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="e81fb-112">Per combinare il nome e la directory di un file per creare il percorso completo</span><span class="sxs-lookup"><span data-stu-id="e81fb-112">To combine a file's name and directory to create the full path</span></span>  
  
- <span data-ttu-id="e81fb-113">Usare il metodo `CombinePath` , specificando la directory e il nome.</span><span class="sxs-lookup"><span data-stu-id="e81fb-113">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="e81fb-114">In questo esempio vengono combinate le stringhe `folderPath` e `fileName` create nell'esempio precedente e viene visualizzato il risultato.</span><span class="sxs-lookup"><span data-stu-id="e81fb-114">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="e81fb-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e81fb-115">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>
- <xref:System.IO.FileInfo>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>
- [<span data-ttu-id="e81fb-116">Procedura: ottenere la raccolta di file di una directory</span><span class="sxs-lookup"><span data-stu-id="e81fb-116">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
