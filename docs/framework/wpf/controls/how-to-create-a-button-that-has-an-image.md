---
title: "Procedura: Creare un pulsante con un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 5be928ac75ad727feabcde07ac0c6dc76ed130e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910949"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="80726-102">Procedura: Creare un pulsante con un'immagine</span><span class="sxs-lookup"><span data-stu-id="80726-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="80726-103">In questo esempio viene illustrato come includere un'immagine su un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="80726-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80726-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="80726-104">Example</span></span>  
 <span data-ttu-id="80726-105">L'esempio seguente crea due <xref:System.Windows.Controls.Button> controlli.</span><span class="sxs-lookup"><span data-stu-id="80726-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="80726-106">Uno <xref:System.Windows.Controls.Button> contiene testo e l'altro contenente un'immagine.</span><span class="sxs-lookup"><span data-stu-id="80726-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="80726-107">L'immagine è in una cartella denominata dati, che sono una sottocartella della cartella del progetto di esempio.</span><span class="sxs-lookup"><span data-stu-id="80726-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="80726-108">Quando un utente sceglie il <xref:System.Windows.Controls.Button> che contiene l'immagine, lo sfondo e il testo di altro <xref:System.Windows.Controls.Button> modificare.</span><span class="sxs-lookup"><span data-stu-id="80726-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="80726-109">Questo esempio viene creato <xref:System.Windows.Controls.Button> controllati tramite markup, ma usa il codice per scrivere il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="80726-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="80726-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80726-110">See also</span></span>

- [<span data-ttu-id="80726-111">Controlli</span><span class="sxs-lookup"><span data-stu-id="80726-111">Controls</span></span>](index.md)
- [<span data-ttu-id="80726-112">Libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="80726-112">Control Library</span></span>](control-library.md)
