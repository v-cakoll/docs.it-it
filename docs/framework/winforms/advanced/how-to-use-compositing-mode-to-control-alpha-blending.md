---
title: 'Procedura: Usare la modalità di composizione per controllare la fusione alfa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590134"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="c0fa1-102">Procedura: Usare la modalità di composizione per controllare la fusione alfa</span><span class="sxs-lookup"><span data-stu-id="c0fa1-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="c0fa1-103">Può accadere quando si desidera creare una bitmap fuori schermo che presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0fa1-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
- <span data-ttu-id="c0fa1-104">Colori abbiano valori alfa minore di 255.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-104">Colors have alpha values that are less than 255.</span></span>  
  
- <span data-ttu-id="c0fa1-105">I colori non sono alfa combinati tra loro quando si crea la bitmap.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
- <span data-ttu-id="c0fa1-106">Quando si visualizza l'immagine bitmap completata, i colori nella mappa di bit sono alfa sfumata con i colori di sfondo sul dispositivo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="c0fa1-107">Per creare una mappa di bit, costruire un valore vuoto <xref:System.Drawing.Bitmap> dell'oggetto e quindi costruire un <xref:System.Drawing.Graphics> oggetto basato sull'immagine.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="c0fa1-108">Impostare la modalità di composizione del <xref:System.Drawing.Graphics> oggetto <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0fa1-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0fa1-109">Example</span></span>  
 <span data-ttu-id="c0fa1-110">L'esempio seguente crea una <xref:System.Drawing.Graphics> oggetto basato su un <xref:System.Drawing.Bitmap> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="c0fa1-111">Il codice Usa il <xref:System.Drawing.Graphics> oggetto insieme ai due pennelli semitrasparenti (alpha = 160) per disegnare sulla bitmap.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="c0fa1-112">Il codice viene compilato un'ellisse rossa e un'ellisse verde usando i pennelli semitrasparenti.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="c0fa1-113">Ellisse di colore verde si sovrappone a rosso puntini di sospensione, ma verde non viene sfumato con il colore rosso perché la modalità di composizione del <xref:System.Drawing.Graphics> è impostata su <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="c0fa1-114">Il codice consente di disegnare la bitmap nella schermata di due volte: una volta su sfondo bianco e una volta su uno sfondo.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="c0fa1-115">I pixel nella bitmap che fanno parte di due ellissi dispone di un componente alfa pari a 160, pertanto i puntini di sospensione vengono combinati con i colori di sfondo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="c0fa1-116">Nella figura seguente mostra l'output dell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="c0fa1-117">Si noti che i puntini di sospensione vengono combinati con lo sfondo, ma non devono essere smussati tra loro.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 ![Diagramma che mostra ellissi sfumato con lo sfondo, non tra loro.](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 <span data-ttu-id="c0fa1-119">L'esempio di codice contiene l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="c0fa1-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="c0fa1-120">Se si desidera che i puntini di sospensione per essere combinati tra loro e con lo sfondo, è possibile modificare tale istruzione come segue:</span><span class="sxs-lookup"><span data-stu-id="c0fa1-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="c0fa1-121">Nella figura seguente mostra l'output del codice modificato.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-121">The following illustration shows the output of the revised code.</span></span>  
  
 ![Diagramma che mostra i puntini di sospensione combinati tra loro e con lo sfondo.](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c0fa1-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c0fa1-123">Compiling the Code</span></span>  
 <span data-ttu-id="c0fa1-124">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0fa1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0fa1-125">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="c0fa1-126">Linee e riempimenti con fusione alfa</span><span class="sxs-lookup"><span data-stu-id="c0fa1-126">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
