---
title: 'Procedura: Salvare file con il controllo RichTextBox di Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: 4784ddd563ccec0f7e6271700781ee1b5d3ac105
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318416"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="d7abe-102">Procedura: Salvare file con il controllo RichTextBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7abe-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="d7abe-103">I moduli di Windows <xref:System.Windows.Forms.RichTextBox> controllo consente di scrivere le informazioni da visualizzare in uno dei seguenti formati:</span><span class="sxs-lookup"><span data-stu-id="d7abe-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>  
  
-   <span data-ttu-id="d7abe-104">Testo normale</span><span class="sxs-lookup"><span data-stu-id="d7abe-104">Plain text</span></span>  
  
-   <span data-ttu-id="d7abe-105">Testo normale Unicode</span><span class="sxs-lookup"><span data-stu-id="d7abe-105">Unicode plain text</span></span>  
  
-   <span data-ttu-id="d7abe-106">Rich-Text Format (RTF)</span><span class="sxs-lookup"><span data-stu-id="d7abe-106">Rich-Text Format (RTF)</span></span>  
  
-   <span data-ttu-id="d7abe-107">RTF con spazi al posto degli oggetti OLE</span><span class="sxs-lookup"><span data-stu-id="d7abe-107">RTF with spaces in place of OLE objects</span></span>  
  
-   <span data-ttu-id="d7abe-108">Testo normale con una rappresentazione testuale di oggetti OLE</span><span class="sxs-lookup"><span data-stu-id="d7abe-108">Plain text with a textual representation of OLE objects</span></span>  
  
 <span data-ttu-id="d7abe-109">Per salvare un file, chiamare il <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="d7abe-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="d7abe-110">È anche possibile usare la **SaveFile** metodo per salvare i dati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="d7abe-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="d7abe-111">Per altre informazioni, vedere <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="d7abe-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="d7abe-112">Per salvare il contenuto del controllo in un file</span><span class="sxs-lookup"><span data-stu-id="d7abe-112">To save the contents of the control to a file</span></span>  
  
1. <span data-ttu-id="d7abe-113">Determinare il percorso del file da salvare.</span><span class="sxs-lookup"><span data-stu-id="d7abe-113">Determine the path of the file to be saved.</span></span>  
  
     <span data-ttu-id="d7abe-114">A tale scopo in un'applicazione reale è in genere si utilizza il <xref:System.Windows.Forms.SaveFileDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="d7abe-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="d7abe-115">Per una panoramica, vedere [Cenni preliminari sul componente SaveFileDialog](savefiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d7abe-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="d7abe-116">Chiamare il <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> metodo di <xref:System.Windows.Forms.RichTextBox> (controllo), specificando il file da salvare e, facoltativamente, un tipo di file.</span><span class="sxs-lookup"><span data-stu-id="d7abe-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="d7abe-117">Se si chiama il metodo con un nome di file come unico argomento, il file verrà salvato in formato RTF.</span><span class="sxs-lookup"><span data-stu-id="d7abe-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="d7abe-118">Per specificare un altro tipo di file, chiamare il metodo con un valore dell'enumerazione <xref:System.Windows.Forms.RichTextBoxStreamType> come secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="d7abe-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="d7abe-119">Nell'esempio seguente, il percorso impostato per il percorso del file RTF è il **documenti** cartella.</span><span class="sxs-lookup"><span data-stu-id="d7abe-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="d7abe-120">Poiché si può presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella, viene usato questo percorso.</span><span class="sxs-lookup"><span data-stu-id="d7abe-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="d7abe-121">Questa scelta consente inoltre agli utenti con livelli di accesso di sistema minimi eseguire in modo sicuro l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7abe-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="d7abe-122">L'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="d7abe-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>  
  
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
    >  <span data-ttu-id="d7abe-123">Questo esempio crea un nuovo file, se il file non esiste.</span><span class="sxs-lookup"><span data-stu-id="d7abe-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="d7abe-124">Se un'applicazione deve creare un file, deve avere accesso Create per la cartella.</span><span class="sxs-lookup"><span data-stu-id="d7abe-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="d7abe-125">Le autorizzazioni vengono impostate tramite gli elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="d7abe-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="d7abe-126">Se il file esiste già, l'applicazione deve solo accesso in scrittura, un privilegio di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="d7abe-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="d7abe-127">Dove possibile, è più sicuro creare il file durante la distribuzione e solo l'accesso in lettura a un singolo file, anziché creare l'accesso per una cartella.</span><span class="sxs-lookup"><span data-stu-id="d7abe-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="d7abe-128">Inoltre, è più sicuro scrivere dati nelle cartelle utente anziché nella cartella radice o nella cartella dei file di programma.</span><span class="sxs-lookup"><span data-stu-id="d7abe-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7abe-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7abe-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="d7abe-130">Controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d7abe-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="d7abe-131">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="d7abe-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
