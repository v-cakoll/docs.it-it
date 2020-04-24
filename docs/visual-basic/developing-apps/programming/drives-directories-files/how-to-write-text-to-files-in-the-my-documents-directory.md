---
title: 'Procedura: scrivere testo in file della directory Documenti'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: bc62f2bc63a2ea185b8ea4c8d271dd28d347d6f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334516"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="523f1-102">Procedura: scrivere testo in file della directory Documenti in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="523f1-102">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>

<span data-ttu-id="523f1-103">L'oggetto `My.Computer.FileSystem.SpecialDirectories` consente di accedere a directory speciali, ad esempio alla directory **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="523f1-103">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="523f1-104">Procedura</span><span class="sxs-lookup"><span data-stu-id="523f1-104">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="523f1-105">Per scrivere nuovo testo nei file della directory Documenti</span><span class="sxs-lookup"><span data-stu-id="523f1-105">To write new text files in the My Documents directory</span></span>  
  
1. <span data-ttu-id="523f1-106">Usare la proprietà `My.Computer.FileSystem.SpecialDirectories.MyDocuments` per specificare il percorso.</span><span class="sxs-lookup"><span data-stu-id="523f1-106">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="523f1-107">Usare il metodo `WriteAllText` per scrivere testo nel file indicato.</span><span class="sxs-lookup"><span data-stu-id="523f1-107">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="523f1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="523f1-108">Example</span></span>  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="523f1-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="523f1-109">Compiling the Code</span></span>  

 <span data-ttu-id="523f1-110">Sostituire `test.txt` con il nome del file in cui si vuole scrivere.</span><span class="sxs-lookup"><span data-stu-id="523f1-110">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="523f1-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="523f1-111">Robust Programming</span></span>  

 <span data-ttu-id="523f1-112">In questo codice vengono rigenerate tutte le eccezioni che possono verificarsi durante la scrittura di testo nel file.</span><span class="sxs-lookup"><span data-stu-id="523f1-112">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="523f1-113">È possibile ridurre la probabilità di eccezioni usando i controlli Windows Form, ad esempio i controlli dei componenti [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) e [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) che limitano le scelte dell'utente a nomi di file validi.</span><span class="sxs-lookup"><span data-stu-id="523f1-113">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) and the [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="523f1-114">L'uso di questi controlli non è comunque infallibile.</span><span class="sxs-lookup"><span data-stu-id="523f1-114">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="523f1-115">Il file system può subire variazioni nel tempo che intercorre tra la selezione di un file da parte dell'utente e il momento in cui il codice viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="523f1-115">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="523f1-116">Quando si usano i file, è quindi quasi sempre necessaria la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="523f1-116">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="523f1-117">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="523f1-117">.NET Framework Security</span></span>  

 <span data-ttu-id="523f1-118">Se eseguito in un contesto ad attendibilità parziale, il codice potrebbe generare un'eccezione a causa dell'insufficienza di privilegi.</span><span class="sxs-lookup"><span data-stu-id="523f1-118">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="523f1-119">Per altre informazioni, vedere [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="523f1-119">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="523f1-120">In questo esempio viene creato un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="523f1-120">This example creates a new file.</span></span> <span data-ttu-id="523f1-121">Per poter creare un file in un'applicazione, è necessario che l'applicazione disponga dell'autorizzazione per la creazione della cartella.</span><span class="sxs-lookup"><span data-stu-id="523f1-121">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="523f1-122">Le autorizzazioni vengono impostate tramite gli elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="523f1-122">Permissions are set using access control lists.</span></span> <span data-ttu-id="523f1-123">Se il file è già esistente, l'applicazione necessita solo dell'autorizzazione di scrittura, ossia di un privilegio di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="523f1-123">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="523f1-124">Laddove possibile, è più sicuro creare il file durante la fase di distribuzione e concedere privilegi di lettura a un unico file, anziché concedere privilegi per la creazione di una cartella.</span><span class="sxs-lookup"><span data-stu-id="523f1-124">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="523f1-125">Inoltre, è più sicuro scrivere i dati nelle cartelle utente anziché nella cartella radice o nella cartella **programmi** .</span><span class="sxs-lookup"><span data-stu-id="523f1-125">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="523f1-126">Per altre informazioni, vedere [Panoramica della tecnologia ACL](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="523f1-126">For more information, see [ACL Technology Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="523f1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="523f1-127">See also</span></span>

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
