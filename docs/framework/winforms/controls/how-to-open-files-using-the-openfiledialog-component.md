---
title: 'Procedura: Aprire i file con il componente OpenFileDialog'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 7f4e96f1714a182647665f12e29d38f2b8037478
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159107"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="8097b-102">Procedura: File aperti con OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="8097b-102">How to: Open files with the OpenFileDialog</span></span> 

<span data-ttu-id="8097b-103">Il <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente consente di aprire la finestra di dialogo di Windows per l'esplorazione e selezione dei file.</span><span class="sxs-lookup"><span data-stu-id="8097b-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="8097b-104">Per aprire e leggere i file selezionati, è possibile usare la <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> metodo, o creare un'istanza del <xref:System.IO.StreamReader?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="8097b-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="8097b-105">Gli esempi seguenti illustrano entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="8097b-105">The following examples show both approaches.</span></span> 

<span data-ttu-id="8097b-106">In .NET Framework, per ottenere o impostare il <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà richiede un livello di privilegio concesso dal <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="8097b-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="8097b-107">Gli esempi eseguono un <xref:System.Security.Permissions.FileIOPermission> autorizzazione controllare e può generare un'eccezione a causa di privilegi sufficienti, se eseguito in un contesto parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="8097b-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="8097b-108">Per altre informazioni, vedere [nozioni fondamentali sulla sicurezza di accesso di codice](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="8097b-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="8097b-109">È possibile compilare ed eseguire questi esempi di come le app .NET Framework dal C# o riga di comando di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8097b-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="8097b-110">Per altre informazioni, vedere [della riga di comando edificio con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oppure [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="8097b-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="8097b-111">A partire da .NET Core 3.0, è possibile anche creare ed eseguire gli esempi come le app .NET Core di Windows da una cartella che dispone di un form di Windows di .NET Core  *\<nome cartella > csproj* file di progetto.</span><span class="sxs-lookup"><span data-stu-id="8097b-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="8097b-112">Esempio: Leggere un file come flusso con StreamReader</span><span class="sxs-lookup"><span data-stu-id="8097b-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="8097b-113">L'esempio seguente usa i moduli di Windows <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore dell'evento per aprire il <xref:System.Windows.Forms.OpenFileDialog> con il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="8097b-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="8097b-114">Dopo che l'utente sceglie un file e seleziona **OK**, un'istanza di <xref:System.IO.StreamReader> legge il file di classe e ne visualizza il contenuto nella casella di testo del form.</span><span class="sxs-lookup"><span data-stu-id="8097b-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="8097b-115">Per altre informazioni sulla lettura da flussi di file, vedere <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> e <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8097b-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="8097b-116">Esempio: Aprire un file da una selezione con OpenFile filtrata</span><span class="sxs-lookup"><span data-stu-id="8097b-116">Example: Open a file from a filtered selection with OpenFile</span></span> 

<span data-ttu-id="8097b-117">L'esempio seguente usa il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore dell'evento per aprire la <xref:System.Windows.Forms.OpenFileDialog> con un filtro che mostra solo i file di testo.</span><span class="sxs-lookup"><span data-stu-id="8097b-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="8097b-118">Dopo che l'utente sceglie un file di testo e seleziona **OK**, il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo viene utilizzato per aprire il file nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="8097b-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="8097b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8097b-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="8097b-120">Componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="8097b-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
