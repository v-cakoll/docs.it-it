---
title: 'Procedura: Leggere il testo da file con un oggetto StreamReader'
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 6d05dac9b612659a74e25c0ce87c7524316d31a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411603"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a><span data-ttu-id="c9d8b-102">Procedura: leggere il testo da file con un oggetto StreamReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9d8b-102">How to: Read Text from Files with a StreamReader (Visual Basic)</span></span>

<span data-ttu-id="c9d8b-103">L'oggetto `My.Computer.FileSystem` offre metodi per aprire <xref:System.IO.TextReader> e <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-103">The `My.Computer.FileSystem` object provides methods to open a <xref:System.IO.TextReader> and a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="c9d8b-104">`OpenTextFileWriter` e `OpenTextFileReader` sono metodi avanzati che non vengono visualizzati in IntelliSense, a meno che non venga selezionata la scheda **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-104">These methods, `OpenTextFileWriter` and `OpenTextFileReader`, are advanced methods that do not appear in IntelliSense unless you select the **All** tab.</span></span>  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a><span data-ttu-id="c9d8b-105">Per leggere una riga da un file con il lettore di testo</span><span class="sxs-lookup"><span data-stu-id="c9d8b-105">To read a line from a file with a text reader</span></span>  
  
- <span data-ttu-id="c9d8b-106">Usare il metodo `OpenTextFileReader` per aprire <xref:System.IO.TextReader>, specificando il file.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-106">Use the `OpenTextFileReader` method to open the <xref:System.IO.TextReader>, specifying the file.</span></span> <span data-ttu-id="c9d8b-107">In questo esempio viene aperto il file denominato `testfile.txt`, da cui una riga viene letta e visualizzata in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-107">This example opens the file named `testfile.txt`, reads a line from it, and displays the line in a message box.</span></span>  
  
     [!code-vb[VbFileIORead#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="c9d8b-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c9d8b-108">Robust Programming</span></span>  

 <span data-ttu-id="c9d8b-109">Il file letto deve essere un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-109">The file that is read must be a text file.</span></span>  
  
 <span data-ttu-id="c9d8b-110">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-110">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="c9d8b-111">È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-111">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="c9d8b-112">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-112">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="c9d8b-113">È possibile che il contenuto del file non corrisponda a quanto previsto e che quindi i metodi per la lettura dal file non abbiano esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-113">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c9d8b-114">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c9d8b-114">.NET Framework Security</span></span>  

 <span data-ttu-id="c9d8b-115">Per leggere da un file, l'assembly richiede un livello di privilegi concesso dalla classe <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-115">To read from a file, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission> class.</span></span> <span data-ttu-id="c9d8b-116">Se eseguito in un contesto ad attendibilità parziale, il codice potrebbe generare un'eccezione a causa dell'insufficienza di privilegi.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-116">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="c9d8b-117">Per altre informazioni, vedere [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="c9d8b-117">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span> <span data-ttu-id="c9d8b-118">È anche necessario che l'utente possa accedere al file.</span><span class="sxs-lookup"><span data-stu-id="c9d8b-118">The user also needs access to the file.</span></span> <span data-ttu-id="c9d8b-119">Per altre informazioni, vedere [Panoramica della tecnologia ACL](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c9d8b-119">For more information, see [ACL Technology Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d8b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9d8b-120">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [<span data-ttu-id="c9d8b-121">Componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="c9d8b-121">SaveFileDialog Component</span></span>](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)
- [<span data-ttu-id="c9d8b-122">Lettura da file</span><span class="sxs-lookup"><span data-stu-id="c9d8b-122">Reading from Files</span></span>](reading-from-files.md)
