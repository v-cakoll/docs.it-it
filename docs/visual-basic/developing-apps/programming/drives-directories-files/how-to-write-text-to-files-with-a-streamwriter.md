---
title: 'Procedura: scrivere testo in file con un oggetto StreamWriter'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
ms.openlocfilehash: 869e29263abcdd8525b2c372c7bb466e3e21fc65
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334491"
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="a7e20-102">Procedura: scrivere testo in file con un oggetto StreamWriter in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7e20-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>

<span data-ttu-id="a7e20-103">In questo esempio viene aperto un oggetto <xref:System.IO.StreamWriter> con il metodo `My.Computer.FileSystem.OpenTextFileWriter` e si usa l'oggetto per scrivere una stringa in un file di testo con il metodo <xref:System.IO.TextWriter.WriteLine%2A> della classe <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="a7e20-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7e20-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7e20-104">Example</span></span>  

 [!code-vb[VbFileIOWrite#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#5)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a7e20-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="a7e20-105">Robust Programming</span></span>  

 <span data-ttu-id="a7e20-106">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="a7e20-106">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="a7e20-107">Il file esiste ed è di sola lettura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a7e20-107">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="a7e20-108">Il disco è pieno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a7e20-108">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="a7e20-109">Il nome del percorso è troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="a7e20-109">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a7e20-110">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a7e20-110">.NET Framework Security</span></span>  

 <span data-ttu-id="a7e20-111">Questo esempio crea un nuovo file, se il file non esiste.</span><span class="sxs-lookup"><span data-stu-id="a7e20-111">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="a7e20-112">Se un'applicazione deve creare un file, deve avere accesso `Create` alla cartella.</span><span class="sxs-lookup"><span data-stu-id="a7e20-112">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="a7e20-113">Se il file esiste già, per l'applicazione è sufficiente l'accesso `Write`, un privilegio di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="a7e20-113">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="a7e20-114">Se possibile, è più sicuro creare il file durante la distribuzione e concedere l'accesso `Read` a un unico file, anziché l'accesso `Create` a una cartella.</span><span class="sxs-lookup"><span data-stu-id="a7e20-114">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e20-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7e20-115">See also</span></span>

- <xref:System.IO.StreamWriter>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- [<span data-ttu-id="a7e20-116">Procedura: Leggere da file di testo</span><span class="sxs-lookup"><span data-stu-id="a7e20-116">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
- [<span data-ttu-id="a7e20-117">Scrittura nei file</span><span class="sxs-lookup"><span data-stu-id="a7e20-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
