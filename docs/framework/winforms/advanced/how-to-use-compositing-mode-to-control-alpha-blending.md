---
title: "Procedura: utilizzare la modalità di composizione per controllare la fusione alfa"
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
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 564d46cb2d72ac63962657b39146489aaafd6a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="cc778-102">Procedura: utilizzare la modalità di composizione per controllare la fusione alfa</span><span class="sxs-lookup"><span data-stu-id="cc778-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="cc778-103">Può accadere quando si desidera creare una bitmap fuori schermo che presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc778-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="cc778-104">Colori hanno valori alfa minore di 255.</span><span class="sxs-lookup"><span data-stu-id="cc778-104">Colors have alpha values that are less than 255.</span></span>  
  
-   <span data-ttu-id="cc778-105">I colori non sono alfa combinati tra loro durante la creazione di bitmap.</span><span class="sxs-lookup"><span data-stu-id="cc778-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
-   <span data-ttu-id="cc778-106">Quando si visualizza l'immagine bitmap completata, i colori nella mappa di bit sono alpha sfumato con i colori di sfondo sul dispositivo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc778-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="cc778-107">Per creare una mappa di bit, creare uno spazio vuoto <xref:System.Drawing.Bitmap> dell'oggetto e quindi creare un <xref:System.Drawing.Graphics> oggetto basato sull'immagine.</span><span class="sxs-lookup"><span data-stu-id="cc778-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="cc778-108">Impostare la modalità di composizione del <xref:System.Drawing.Graphics> oggetto <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cc778-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc778-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc778-109">Example</span></span>  
 <span data-ttu-id="cc778-110">Nell'esempio seguente viene creato un <xref:System.Drawing.Graphics> oggetto basato su un <xref:System.Drawing.Bitmap> oggetto.</span><span class="sxs-lookup"><span data-stu-id="cc778-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="cc778-111">Il codice Usa il <xref:System.Drawing.Graphics> oggetto insieme a due pennelli semitrasparenti (alfa = 160) per colorare l'immagine bitmap.</span><span class="sxs-lookup"><span data-stu-id="cc778-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="cc778-112">Il codice verrà inserito un'ellisse rossa e un'ellisse verde mediante i pennelli semitrasparenti.</span><span class="sxs-lookup"><span data-stu-id="cc778-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="cc778-113">Ellisse di colore verde si sovrappone colore rosso, ma il verde non viene sfumato con il rosso perché la modalità di composizione del <xref:System.Drawing.Graphics> oggetto è impostato su <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span><span class="sxs-lookup"><span data-stu-id="cc778-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="cc778-114">Il codice la bitmap disegnata sullo schermo due volte: una volta su sfondo bianco e una volta su uno sfondo.</span><span class="sxs-lookup"><span data-stu-id="cc778-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="cc778-115">Il pixel della bitmap che fanno parte di due ellissi presentano un componente alfa di 160, pertanto i puntini di sospensione sono combinati con i colori di sfondo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="cc778-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="cc778-116">Nella figura seguente mostra l'output dell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="cc778-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="cc778-117">Si noti che i puntini di sospensione sono combinati con lo sfondo, ma non sono combinati tra loro.</span><span class="sxs-lookup"><span data-stu-id="cc778-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 <span data-ttu-id="cc778-118">![Copia di origine](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span><span class="sxs-lookup"><span data-stu-id="cc778-118">![Source Copy](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span></span>  
  
 <span data-ttu-id="cc778-119">L'esempio di codice contiene questa istruzione:</span><span class="sxs-lookup"><span data-stu-id="cc778-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="cc778-120">Se si desidera i puntini di sospensione per essere combinati tra loro e con lo sfondo, è possibile modificare l'istruzione per le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc778-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="cc778-121">Nella figura seguente mostra l'output del codice modificato.</span><span class="sxs-lookup"><span data-stu-id="cc778-121">The following illustration shows the output of the revised code.</span></span>  
  
 <span data-ttu-id="cc778-122">![Origine su](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span><span class="sxs-lookup"><span data-stu-id="cc778-122">![Source Over](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cc778-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="cc778-123">Compiling the Code</span></span>  
 <span data-ttu-id="cc778-124">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="cc778-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc778-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc778-125">See Also</span></span>  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [<span data-ttu-id="cc778-126">Linee e riempimenti con fusione alfa</span><span class="sxs-lookup"><span data-stu-id="cc778-126">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
