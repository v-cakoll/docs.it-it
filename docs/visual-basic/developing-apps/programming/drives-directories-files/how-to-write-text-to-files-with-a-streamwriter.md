---
title: 'Procedura: scrivere testo in file con un oggetto StreamWriter in Visual Basic'
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
- files, writing to
- text, writing to files
- writing to files, StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
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
ms.openlocfilehash: ea85d57e9af4fdd640733db5dc2fa8b0ab25325c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="0a908-102">Procedura: scrivere testo in file con un oggetto StreamWriter in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a908-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="0a908-103">In questo esempio viene aperto un oggetto <xref:System.IO.StreamWriter> con il metodo `My.Computer.FileSystem.OpenTextFileWriter` e si usa l'oggetto per scrivere una stringa in un file di testo con il metodo <xref:System.IO.TextWriter.WriteLine%2A> della classe <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="0a908-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a908-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a908-104">Example</span></span>  
 <span data-ttu-id="0a908-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0a908-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0a908-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="0a908-106">Robust Programming</span></span>  
 <span data-ttu-id="0a908-107">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="0a908-107">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0a908-108">Il file esiste ed è di sola lettura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="0a908-108">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="0a908-109">Il disco è pieno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="0a908-109">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="0a908-110">Il nome del percorso è troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="0a908-110">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="0a908-111">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0a908-111">.NET Framework Security</span></span>  
 <span data-ttu-id="0a908-112">Questo esempio crea un nuovo file, se il file non esiste.</span><span class="sxs-lookup"><span data-stu-id="0a908-112">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="0a908-113">Se un'applicazione deve creare un file, deve avere accesso `Create` alla cartella.</span><span class="sxs-lookup"><span data-stu-id="0a908-113">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="0a908-114">Se il file esiste già, per l'applicazione è sufficiente l'accesso `Write`, un privilegio di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="0a908-114">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="0a908-115">Se possibile, è più sicuro creare il file durante la distribuzione e concedere l'accesso `Read` a un unico file, anziché l'accesso `Create` a una cartella.</span><span class="sxs-lookup"><span data-stu-id="0a908-115">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a908-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a908-116">See Also</span></span>  
 <span data-ttu-id="0a908-117"><xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="0a908-117"><xref:System.IO.StreamWriter></span></span>   
 <span data-ttu-id="0a908-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span><span class="sxs-lookup"><span data-stu-id="0a908-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span></span>   
 <span data-ttu-id="0a908-119">[Procedura: Leggere da file di testo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="0a908-119">[How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span></span>  
 [<span data-ttu-id="0a908-120">Scrittura su file</span><span class="sxs-lookup"><span data-stu-id="0a908-120">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)

