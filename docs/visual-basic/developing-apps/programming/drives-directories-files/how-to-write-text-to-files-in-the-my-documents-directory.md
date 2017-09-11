---
title: 'Procedura: scrivere testo in file della directory Documenti in Visual Basic'
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
- examples [Visual Basic], text files
- writing to files, in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
caps.latest.revision: 19
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
ms.openlocfilehash: c900072d184469ead75bb76a3e152edce357a34f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="a35e3-102">Procedura: scrivere testo in file della directory Documenti in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a35e3-102">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="a35e3-103">L'oggetto `My.Computer.FileSystem.SpecialDirectories` consente di accedere a directory speciali, ad esempio alla directory **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="a35e3-103">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="a35e3-104">Procedura</span><span class="sxs-lookup"><span data-stu-id="a35e3-104">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="a35e3-105">Per scrivere nuovo testo nei file della directory Documenti</span><span class="sxs-lookup"><span data-stu-id="a35e3-105">To write new text files in the My Documents directory</span></span>  
  
1.  <span data-ttu-id="a35e3-106">Usare la proprietà `My.Computer.FileSystem.SpecialDirectories.MyDocuments` per specificare il percorso.</span><span class="sxs-lookup"><span data-stu-id="a35e3-106">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     <span data-ttu-id="a35e3-107">[!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35e3-107">[!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]</span></span>  
  
2.  <span data-ttu-id="a35e3-108">Usare il metodo `WriteAllText` per scrivere testo nel file indicato.</span><span class="sxs-lookup"><span data-stu-id="a35e3-108">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     <span data-ttu-id="a35e3-109">[!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35e3-109">[!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a35e3-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="a35e3-110">Example</span></span>  
 <span data-ttu-id="a35e3-111">[!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35e3-111">[!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a35e3-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a35e3-112">Compiling the Code</span></span>  
 <span data-ttu-id="a35e3-113">Sostituire `test.txt` con il nome del file in cui si vuole scrivere.</span><span class="sxs-lookup"><span data-stu-id="a35e3-113">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a35e3-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="a35e3-114">Robust Programming</span></span>  
 <span data-ttu-id="a35e3-115">In questo codice vengono rigenerate tutte le eccezioni che possono verificarsi durante la scrittura di testo nel file.</span><span class="sxs-lookup"><span data-stu-id="a35e3-115">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="a35e3-116">È possibile ridurre la probabilità di eccezioni usando i controlli Windows Form, ad esempio i controlli dei componenti [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) e [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) che limitano le scelte dell'utente a nomi di file validi.</span><span class="sxs-lookup"><span data-stu-id="a35e3-116">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) and the [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="a35e3-117">L'uso di questi controlli non è comunque infallibile.</span><span class="sxs-lookup"><span data-stu-id="a35e3-117">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="a35e3-118">Il file system può subire variazioni nel tempo che intercorre tra la selezione di un file da parte dell'utente e il momento in cui il codice viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="a35e3-118">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="a35e3-119">Quando si usano i file, è quindi quasi sempre necessaria la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="a35e3-119">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a35e3-120">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a35e3-120">.NET Framework Security</span></span>  
 <span data-ttu-id="a35e3-121">Se eseguito in un contesto ad attendibilità parziale, il codice potrebbe generare un'eccezione a causa dell'insufficienza di privilegi.</span><span class="sxs-lookup"><span data-stu-id="a35e3-121">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="a35e3-122">Per altre informazioni, vedere [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="a35e3-122">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
 <span data-ttu-id="a35e3-123">In questo esempio viene creato un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="a35e3-123">This example creates a new file.</span></span> <span data-ttu-id="a35e3-124">Per poter creare un file in un'applicazione, è necessario che l'applicazione disponga dell'autorizzazione per la creazione della cartella.</span><span class="sxs-lookup"><span data-stu-id="a35e3-124">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="a35e3-125">Le autorizzazioni vengono impostate tramite gli elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="a35e3-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="a35e3-126">Se il file è già esistente, l'applicazione necessita solo dell'autorizzazione di scrittura, ossia di un privilegio di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="a35e3-126">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="a35e3-127">Laddove possibile, è più sicuro creare il file durante la fase di distribuzione e concedere privilegi di lettura a un unico file, anziché concedere privilegi per la creazione di una cartella.</span><span class="sxs-lookup"><span data-stu-id="a35e3-127">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="a35e3-128">È anche più sicuro scrivere i dati nelle cartelle utente anziché nella cartella radice o nella cartella **Programmi**.</span><span class="sxs-lookup"><span data-stu-id="a35e3-128">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="a35e3-129">Per altre informazioni, vedere [Panoramica della tecnologia ACL](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span><span class="sxs-lookup"><span data-stu-id="a35e3-129">For more information, see [ACL Technology Overview](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a35e3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a35e3-130">See Also</span></span>  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>

