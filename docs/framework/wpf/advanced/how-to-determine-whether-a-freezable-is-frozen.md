---
title: 'Procedura: Determinare se un oggetto Freezable è bloccato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 005bb27803830a2e38a7b143d2c4cff669ad1da6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362513"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="2b64f-102">Procedura: Determinare se un oggetto Freezable è bloccato</span><span class="sxs-lookup"><span data-stu-id="2b64f-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="2b64f-103">In questo esempio viene illustrato come determinare se un <xref:System.Windows.Freezable> oggetto è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="2b64f-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="2b64f-104">Se si prova a modificare un oggetto bloccato <xref:System.Windows.Freezable> dell'oggetto, genera un <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="2b64f-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="2b64f-105">Per evitare la generazione di questa eccezione, usare il <xref:System.Windows.Freezable.IsFrozen%2A> proprietà del <xref:System.Windows.Freezable> oggetto per determinare se è bloccato.</span><span class="sxs-lookup"><span data-stu-id="2b64f-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b64f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b64f-106">Example</span></span>  
 <span data-ttu-id="2b64f-107">Nell'esempio seguente si blocca una <xref:System.Windows.Media.SolidColorBrush> e quindi verifica l'evento utilizzando il <xref:System.Windows.Freezable.IsFrozen%2A> proprietà per determinare se è bloccato.</span><span class="sxs-lookup"><span data-stu-id="2b64f-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="2b64f-108">Per altre informazioni sulle <xref:System.Windows.Freezable> oggetti, vedere la [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2b64f-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b64f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b64f-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="2b64f-110">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="2b64f-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="2b64f-111">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="2b64f-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
