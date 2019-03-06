---
title: "Procedura: Eseguire l'override del metodo Panel OnRender"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: cefeee320e10a9e9de0d38894d4d865ca2e639ec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368952"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="b729a-102">Procedura: Eseguire l'override del metodo Panel OnRender</span><span class="sxs-lookup"><span data-stu-id="b729a-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="b729a-103">Questo esempio illustra come eseguire l'override di <xref:System.Windows.Controls.Panel.OnRender%2A> metodo <xref:System.Windows.Controls.Panel> per aggiungere effetti grafici personalizzati a un elemento di layout.</span><span class="sxs-lookup"><span data-stu-id="b729a-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b729a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b729a-104">Example</span></span>  
 <span data-ttu-id="b729a-105">Usare il <xref:System.Windows.Controls.Panel.OnRender%2A> metodo per aggiungere effetti grafici a un elemento panel sottoposto a rendering.</span><span class="sxs-lookup"><span data-stu-id="b729a-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="b729a-106">Ad esempio, è possibile usare questo metodo per aggiungere personalizzata del bordo o sfondo effetti.</span><span class="sxs-lookup"><span data-stu-id="b729a-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="b729a-107">Oggetto <xref:System.Windows.Media.DrawingContext> oggetto viene passato come argomento, che fornisce i metodi per disegnare forme, testo, immagini o video.</span><span class="sxs-lookup"><span data-stu-id="b729a-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="b729a-108">Di conseguenza, questo metodo è utile per la personalizzazione di un oggetto panel.</span><span class="sxs-lookup"><span data-stu-id="b729a-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b729a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b729a-109">See also</span></span>
- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="b729a-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="b729a-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="b729a-111">Esempio di pannello radiale personalizzato</span><span class="sxs-lookup"><span data-stu-id="b729a-111">Custom Radial Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159982)
- [<span data-ttu-id="b729a-112">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b729a-112">How-to Topics</span></span>](panel-how-to-topics.md)
