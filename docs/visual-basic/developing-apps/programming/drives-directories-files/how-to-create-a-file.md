---
title: 'Procedura: creare un file in Visual Basic'
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
- text files, creating
- files, creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
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
ms.openlocfilehash: d06d274b31afad0a437405d1679e0be7548f2e14
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="c8a2c-102">Procedura: creare un file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8a2c-102">How to: Create a File in Visual Basic</span></span>
<span data-ttu-id="c8a2c-103">In questo esempio viene creato un file di testo vuoto nel percorso specificato usando il metodo <xref:System.IO.File.Create%2A> nella classe <xref:System.IO.File>.</span><span class="sxs-lookup"><span data-stu-id="c8a2c-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8a2c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8a2c-104">Example</span></span>  
 <span data-ttu-id="c8a2c-105">[!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c8a2c-105">[!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8a2c-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c8a2c-106">Compiling the Code</span></span>  
 <span data-ttu-id="c8a2c-107">Usare la variabile `file` per scrivere il file.</span><span class="sxs-lookup"><span data-stu-id="c8a2c-107">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c8a2c-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c8a2c-108">Robust Programming</span></span>  
 <span data-ttu-id="c8a2c-109">Se il file esiste già, viene sostituito.</span><span class="sxs-lookup"><span data-stu-id="c8a2c-109">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="c8a2c-110">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="c8a2c-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="c8a2c-111">Il nome del percorso non è valido.</span><span class="sxs-lookup"><span data-stu-id="c8a2c-111">The path name is malformed.</span></span> <span data-ttu-id="c8a2c-112">Contiene ad esempio caratteri non validi o è costituito solo da uno spazio (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c8a2c-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="c8a2c-113">Il percorso è di sola lettura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="c8a2c-113">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="c8a2c-114">Il nome del percorso è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c8a2c-114">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="c8a2c-115">Il nome del percorso è troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="c8a2c-115">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="c8a2c-116">Il percorso non è valido (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="c8a2c-116">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="c8a2c-117">Il percorso contiene solo due punti ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="c8a2c-117">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c8a2c-118">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c8a2c-118">.NET Framework Security</span></span>  
 <span data-ttu-id="c8a2c-119">È possibile che venga generata un'eccezione <xref:System.Security.SecurityException> in ambienti ad attendibilità parziale.</span><span class="sxs-lookup"><span data-stu-id="c8a2c-119">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="c8a2c-120">La chiamata al metodo <xref:System.IO.File.Create%2A> richiede <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="c8a2c-120">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="c8a2c-121">Viene generata un'eccezione <xref:System.UnauthorizedAccessException> se l'utente non dispone dell'autorizzazione per creare il file.</span><span class="sxs-lookup"><span data-stu-id="c8a2c-121">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a2c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8a2c-122">See Also</span></span>  
 <span data-ttu-id="c8a2c-123"><xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="c8a2c-123"><xref:System.IO></span></span>   
 <span data-ttu-id="c8a2c-124"><xref:System.IO.File.Create%2A></span><span class="sxs-lookup"><span data-stu-id="c8a2c-124"><xref:System.IO.File.Create%2A></span></span>   
 <span data-ttu-id="c8a2c-125">[Uso di librerie da codice parzialmente attendibile](../../../../framework/misc/using-libraries-from-partially-trusted-code.md) </span><span class="sxs-lookup"><span data-stu-id="c8a2c-125">[Using Libraries from Partially Trusted Code](../../../../framework/misc/using-libraries-from-partially-trusted-code.md) </span></span>  
 [<span data-ttu-id="c8a2c-126">Nozioni fondamentali sulla sicurezza per l’accesso al codice</span><span class="sxs-lookup"><span data-stu-id="c8a2c-126">Code Access Security Basics</span></span>](https://msdn.microsoft.com/library/33tceax8)

