---
title: 'Procedura: salvare file con il controllo RichTextBox Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d28aeaefca6f8aa13607f1c1e6f72557ef536754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="4796f-102">Procedura: salvare file con il controllo RichTextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="4796f-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="4796f-103">Windows Form <xref:System.Windows.Forms.RichTextBox> controllo consente di scrivere le informazioni da visualizzare in uno dei seguenti formati:</span><span class="sxs-lookup"><span data-stu-id="4796f-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>  
  
-   <span data-ttu-id="4796f-104">Testo normale</span><span class="sxs-lookup"><span data-stu-id="4796f-104">Plain text</span></span>  
  
-   <span data-ttu-id="4796f-105">Testo normale Unicode</span><span class="sxs-lookup"><span data-stu-id="4796f-105">Unicode plain text</span></span>  
  
-   <span data-ttu-id="4796f-106">Il formato RTF (RICH)</span><span class="sxs-lookup"><span data-stu-id="4796f-106">Rich-Text Format (RTF)</span></span>  
  
-   <span data-ttu-id="4796f-107">RTF con spazi al posto di oggetti OLE</span><span class="sxs-lookup"><span data-stu-id="4796f-107">RTF with spaces in place of OLE objects</span></span>  
  
-   <span data-ttu-id="4796f-108">Testo normale con una rappresentazione testuale di oggetti OLE</span><span class="sxs-lookup"><span data-stu-id="4796f-108">Plain text with a textual representation of OLE objects</span></span>  
  
 <span data-ttu-id="4796f-109">Per salvare un file, chiamare il <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="4796f-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="4796f-110">È inoltre possibile utilizzare il **SaveFile** per salvare i dati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="4796f-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="4796f-111">Per altre informazioni, vedere <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="4796f-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="4796f-112">Per salvare il contenuto del controllo in un file</span><span class="sxs-lookup"><span data-stu-id="4796f-112">To save the contents of the control to a file</span></span>  
  
1.  <span data-ttu-id="4796f-113">Determinare il percorso del file da salvare.</span><span class="sxs-lookup"><span data-stu-id="4796f-113">Determine the path of the file to be saved.</span></span>  
  
     <span data-ttu-id="4796f-114">Per eseguire questa operazione in un'applicazione reale, in genere si utilizzerà il <xref:System.Windows.Forms.SaveFileDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="4796f-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="4796f-115">Per una panoramica, vedere [Cenni preliminari sul componente SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4796f-115">For an overview, see [SaveFileDialog Component Overview](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="4796f-116">Chiamare il <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> metodo il <xref:System.Windows.Forms.RichTextBox> (controllo), specificando il file da salvare e, facoltativamente, un tipo di file.</span><span class="sxs-lookup"><span data-stu-id="4796f-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="4796f-117">Se si chiama il metodo con un nome di file come unico argomento, il file verrà salvato in formato RTF.</span><span class="sxs-lookup"><span data-stu-id="4796f-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="4796f-118">Per specificare un altro tipo di file, chiamare il metodo con un valore dell'enumerazione <xref:System.Windows.Forms.RichTextBoxStreamType> come secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="4796f-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="4796f-119">Nell'esempio seguente, il percorso impostato per il percorso del file RTF è il **documenti** cartella.</span><span class="sxs-lookup"><span data-stu-id="4796f-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="4796f-120">Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="4796f-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="4796f-121">Questa scelta consente anche agli utenti con livelli di accesso di sistema minimi eseguire in modo sicuro l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4796f-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="4796f-122">Nell'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="4796f-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>  
  
    ```vb  
    Public Sub SaveFile()  
       ' You should replace the bold file name in the   
       ' sample below with a file name of your own choosing.  
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Testdoc.rtf", _  
          RichTextBoxStreamType.RichNoOleObjs)  
    End Sub  
    ```  
  
    ```csharp  
    public void SaveFile()  
    {  
       // You should replace the bold file name in the   
       // sample below with a file name of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       richTextBox1.SaveFile(System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Testdoc.rtf",  
          RichTextBoxStreamType.RichNoOleObjs);  
    }  
    ```  
  
    ```cpp  
    public:  
       void SaveFile()  
       {  
          // You should replace the bold file name in the   
          // sample below with a file name of your own choosing.  
          richTextBox1->SaveFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4796f-123">Questo esempio crea un nuovo file, se il file non esiste.</span><span class="sxs-lookup"><span data-stu-id="4796f-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="4796f-124">Se un'applicazione deve creare un file, tale applicazione richiede accesso Create per la cartella.</span><span class="sxs-lookup"><span data-stu-id="4796f-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="4796f-125">Le autorizzazioni vengono impostate tramite gli elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4796f-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="4796f-126">Se il file esiste già, l'applicazione deve solo accesso in scrittura, un privilegio minore.</span><span class="sxs-lookup"><span data-stu-id="4796f-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="4796f-127">Dove possibile, è più sicuro per creare il file durante la distribuzione e concedere solo accesso in lettura a un singolo file, anziché creare l'accesso per una cartella.</span><span class="sxs-lookup"><span data-stu-id="4796f-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="4796f-128">Inoltre, è più sicuro scrivere dati nelle cartelle utente anziché nella cartella radice o nella cartella dei file di programma.</span><span class="sxs-lookup"><span data-stu-id="4796f-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4796f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4796f-129">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="4796f-130">Controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="4796f-130">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="4796f-131">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4796f-131">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
