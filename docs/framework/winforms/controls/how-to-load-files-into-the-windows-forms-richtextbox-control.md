---
title: Carica i file nel controllo RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
ms.openlocfilehash: c31e004ea4cd0821b5f18f0ab0fe2708e6ac4b59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736293"
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a><span data-ttu-id="85093-102">Procedura: caricare file nel controllo RichTextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="85093-102">How to: Load Files into the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="85093-103">Il controllo <xref:System.Windows.Forms.RichTextBox> Windows Form consente di visualizzare un file come testo normale, testo normale Unicode o in formato RTF (Rich-Text Format).</span><span class="sxs-lookup"><span data-stu-id="85093-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display a plain-text, Unicode plain-text, or Rich-Text-Format (RTF) file.</span></span> <span data-ttu-id="85093-104">Per eseguire questa operazione, chiamare il metodo <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> .</span><span class="sxs-lookup"><span data-stu-id="85093-104">To do so, call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method.</span></span> <span data-ttu-id="85093-105">È anche possibile usare <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> per caricare dati da un flusso.</span><span class="sxs-lookup"><span data-stu-id="85093-105">You can also use the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method to load data from a stream.</span></span> <span data-ttu-id="85093-106">Per altre informazioni, vedere <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="85093-106">For more information, see <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-load-a-file-into-the-richtextbox-control"></a><span data-ttu-id="85093-107">Per caricare un file nel controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="85093-107">To load a file into the RichTextBox control</span></span>

1. <span data-ttu-id="85093-108">Determinare il percorso del file da aprire usando il componente <xref:System.Windows.Forms.OpenFileDialog> .</span><span class="sxs-lookup"><span data-stu-id="85093-108">Determine the path of the file to be opened using the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="85093-109">Per una panoramica, vedere [Cenni preliminari sul componente OpenFileDialog](openfiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="85093-109">For an overview, see [OpenFileDialog Component Overview](openfiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="85093-110">Chiamare il metodo <xref:System.Windows.Forms.RichTextBox.LoadFile%2A><xref:System.Windows.Forms.RichTextBox> specificando il file da caricare e, facoltativamente, un tipo di file.</span><span class="sxs-lookup"><span data-stu-id="85093-110">Call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to load and optionally a file type.</span></span> <span data-ttu-id="85093-111">Nell'esempio seguente il file da caricare viene preso dalla proprietà <xref:System.Windows.Forms.OpenFileDialog> del componente <xref:System.Windows.Forms.FileDialog.FileName%2A> .</span><span class="sxs-lookup"><span data-stu-id="85093-111">In the example below, the file to load is taken from the <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.FileDialog.FileName%2A> property.</span></span> <span data-ttu-id="85093-112">Se si chiama il metodo usando come unico argomento un nome di file, si presuppone che il tipo del file sia RTF.</span><span class="sxs-lookup"><span data-stu-id="85093-112">If you call the method with a file name as its only argument, the file type will be assumed to be RTF.</span></span> <span data-ttu-id="85093-113">Per specificare un altro tipo di file, chiamare il metodo con un valore dell'enumerazione <xref:System.Windows.Forms.RichTextBoxStreamType> come secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="85093-113">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="85093-114">Nell'esempio seguente viene visualizzato il componente <xref:System.Windows.Forms.OpenFileDialog> quando si fa clic su un pulsante.</span><span class="sxs-lookup"><span data-stu-id="85093-114">In the example below, the <xref:System.Windows.Forms.OpenFileDialog> component is shown when a button is clicked.</span></span> <span data-ttu-id="85093-115">Il file selezionato viene quindi aperto e visualizzato nel controllo <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="85093-115">The file selected is then opened and displayed in the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="85093-116">In questo esempio si presuppone l'esistenza di un form contenente un pulsante`btnOpenFile`.</span><span class="sxs-lookup"><span data-stu-id="85093-116">This example assumes a form has a button,`btnOpenFile`.</span></span>

    ```vb
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _
       ByVal e As System.EventArgs) Handles btnOpenFile.Click
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _
              RichTextBoxStreamType.RichText)
          End If
    End Sub
    ```

    ```csharp
    private void btnOpenFile_Click(object sender, System.EventArgs e)
    {
       if(openFileDialog1.ShowDialog() == DialogResult.OK)
       {
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);
       }
    }
    ```

    ```cpp
    private:
       void btnOpenFile_Click(System::Object ^  sender,
          System::EventArgs ^  e)
       {
          if(openFileDialog1->ShowDialog() == DialogResult::OK)
          {
             richTextBox1->LoadFile(openFileDialog1->FileName,
                RichTextBoxStreamType::RichText);
          }
       }
    ```

    <span data-ttu-id="85093-117">(Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="85093-117">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

    ```csharp
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);
    ```

    ```cpp
    this->btnOpenFile->Click += gcnew
       System::EventHandler(this, &Form1::btnOpenFile_Click);
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="85093-118">Per eseguire questo processo, l'assembly può richiede un livello di privilegio concesso dalla classe <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="85093-118">To run this process, your assembly may require a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="85093-119">Se l'esecuzione avviene in un contesto parzialmente attendibile, è possibile che il processo generi un'eccezione dovuta a privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="85093-119">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="85093-120">Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="85093-120">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="85093-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85093-121">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="85093-122">Controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="85093-122">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="85093-123">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="85093-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
