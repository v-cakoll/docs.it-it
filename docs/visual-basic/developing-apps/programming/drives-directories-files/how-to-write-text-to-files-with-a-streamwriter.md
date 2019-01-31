---
title: 'Procedura: Scrivere testo in file con un oggetto StreamWriter in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
ms.openlocfilehash: 39c6ad59ad965f566c77f72dd4a97335494d6382
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678525"
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="4414c-102">Procedura: Scrivere testo in file con un oggetto StreamWriter in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4414c-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="4414c-103">In questo esempio viene aperto un oggetto <xref:System.IO.StreamWriter> con il metodo `My.Computer.FileSystem.OpenTextFileWriter` e si usa l'oggetto per scrivere una stringa in un file di testo con il metodo <xref:System.IO.TextWriter.WriteLine%2A> della classe <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="4414c-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4414c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4414c-104">Example</span></span>  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="4414c-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="4414c-105">Robust Programming</span></span>  
 <span data-ttu-id="4414c-106">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="4414c-106">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="4414c-107">Il file esiste ed è di sola lettura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4414c-107">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4414c-108">Il disco è pieno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4414c-108">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4414c-109">Il nome del percorso è troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="4414c-109">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4414c-110">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4414c-110">.NET Framework Security</span></span>  
 <span data-ttu-id="4414c-111">Questo esempio crea un nuovo file, se il file non esiste.</span><span class="sxs-lookup"><span data-stu-id="4414c-111">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="4414c-112">Se un'applicazione deve creare un file, deve avere accesso `Create` alla cartella.</span><span class="sxs-lookup"><span data-stu-id="4414c-112">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="4414c-113">Se il file esiste già, per l'applicazione è sufficiente l'accesso `Write`, un privilegio di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="4414c-113">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="4414c-114">Se possibile, è più sicuro creare il file durante la distribuzione e concedere l'accesso `Read` a un unico file, anziché l'accesso `Create` a una cartella.</span><span class="sxs-lookup"><span data-stu-id="4414c-114">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4414c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4414c-115">See also</span></span>
- <xref:System.IO.StreamWriter>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- [<span data-ttu-id="4414c-116">Procedura: Leggere da file di testo</span><span class="sxs-lookup"><span data-stu-id="4414c-116">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
- [<span data-ttu-id="4414c-117">Scrittura su file</span><span class="sxs-lookup"><span data-stu-id="4414c-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
