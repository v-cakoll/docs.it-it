---
title: "Procedura: Impostare l'immagine visualizzata da un controllo di Windows Forms"
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: b1b1dbbb50c3b19cf8d8a7d7030d0bc168afb6a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666194"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="d3fcf-102">Procedura: Imposta l'immagine visualizzata da un controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3fcf-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="d3fcf-103">Diversi controlli Windows Forms possono visualizzare immagini.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="d3fcf-104">Queste immagini possono essere icone che chiariscono lo scopo del controllo, ad esempio un'icona a forma di dischetto in un pulsante che indica il comando Salva.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="d3fcf-105">In alternativa, le icone possono essere immagini di sfondo per dare al controllo l'aspetto e il comportamento desiderati.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="programmatic"></a><span data-ttu-id="d3fcf-106">A livello</span><span class="sxs-lookup"><span data-stu-id="d3fcf-106">Programmatic</span></span>

<span data-ttu-id="d3fcf-107">Impostare la proprietà `Image` o `BackgroundImage` del controllo su un oggetto di tipo <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="d3fcf-108">In genere, è possibile caricare l'immagine da un file usando il <xref:System.Drawing.Image.FromFile%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-108">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="d3fcf-109">Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **Immagini personali** .</span><span class="sxs-lookup"><span data-stu-id="d3fcf-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="d3fcf-110">La maggior parte dei computer che eseguono il sistema operativo Windows include questa directory.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-110">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="d3fcf-111">Consente inoltre agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="d3fcf-112">Nell'esempio di codice seguente è necessario avere già un modulo con un <xref:System.Windows.Forms.PictureBox> controllo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a><span data-ttu-id="d3fcf-113">Designer</span><span class="sxs-lookup"><span data-stu-id="d3fcf-113">Designer</span></span>

1. <span data-ttu-id="d3fcf-114">Nella finestra **Proprietà** di Visual Studio selezionare la proprietà **Image** o **BackgroundImage** del controllo, quindi selezionare i puntini di sospensione (![pulsante con i puntini di sospensione in Visual Studio](./media/visual-studio-ellipsis-button.png)) per visualizzare la **selezione** Finestra di dialogo risorsa.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-114">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](./media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box.</span></span>

2. <span data-ttu-id="d3fcf-115">Selezionare l'immagine che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="d3fcf-115">Select the image you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3fcf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3fcf-116">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
