---
title: 'Procedura: Usare SystemParameters'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4b2ee3956017e10da8adda52fa9a0ec31cb19ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-systemparameters"></a><span data-ttu-id="50426-102">Procedura: Usare SystemParameters</span><span class="sxs-lookup"><span data-stu-id="50426-102">How to: Use SystemParameters</span></span>
<span data-ttu-id="50426-103">In questo esempio viene illustrato come accedere e utilizzare le proprietà di <xref:System.Windows.SystemParameters> per applicare uno stile o personalizzare un pulsante.</span><span class="sxs-lookup"><span data-stu-id="50426-103">This example shows how to access and use the properties of <xref:System.Windows.SystemParameters> in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50426-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="50426-104">Example</span></span>  
 <span data-ttu-id="50426-105">Le risorse di sistema espongono diverse impostazioni basate sul sistema come risorse per consentire la creazione di oggetti visivi coerenti con le impostazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="50426-105">System resources expose several system based settings as resources in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="50426-106"><xref:System.Windows.SystemParameters>è una classe che contiene le proprietà valore di parametro di sistema e le chiavi di risorsa che l'associazione ai valori.</span><span class="sxs-lookup"><span data-stu-id="50426-106"><xref:System.Windows.SystemParameters> is a class that contains both system parameter value properties, and resource keys that bind to the values.</span></span> <span data-ttu-id="50426-107">Ad esempio, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> è un <xref:System.Windows.SystemParameters> valore della proprietà e <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> è la chiave di risorsa corrispondente.</span><span class="sxs-lookup"><span data-stu-id="50426-107">For example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> is a <xref:System.Windows.SystemParameters> property value and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> is the corresponding resource key.</span></span>  
  
 <span data-ttu-id="50426-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile utilizzare i membri di <xref:System.Windows.SystemParameters> come l'utilizzo di una proprietà statica o un riferimento di risorsa dinamica (con il valore della proprietà statica come chiave).</span><span class="sxs-lookup"><span data-stu-id="50426-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemParameters> as either a static property usage, or a dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="50426-109">Usare un riferimento alla risorsa dinamica per aggiornare automaticamente il valore basato sul sistema durante l'esecuzione dell'applicazione; in caso contrario, usare un riferimento statico.</span><span class="sxs-lookup"><span data-stu-id="50426-109">Use a dynamic resource reference if you want the system based value to update automatically while the application runs; otherwise, use a static reference.</span></span> <span data-ttu-id="50426-110">Le chiavi di risorsa hanno il suffisso `Key` aggiunto al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="50426-110">Resource keys have the suffix `Key` appended to the property name.</span></span>  
  
 <span data-ttu-id="50426-111">Nell'esempio seguente viene illustrato come accedere e utilizzare i valori statici di <xref:System.Windows.SystemParameters> per applicare uno stile o personalizzare un pulsante.</span><span class="sxs-lookup"><span data-stu-id="50426-111">The following example shows how to access and use the static values of <xref:System.Windows.SystemParameters> to style or customize a button.</span></span> <span data-ttu-id="50426-112">In questo esempio di markup con dimensioni applicando un pulsante <xref:System.Windows.SystemParameters> valori a un pulsante.</span><span class="sxs-lookup"><span data-stu-id="50426-112">This markup example sizes a button by applying <xref:System.Windows.SystemParameters> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 <span data-ttu-id="50426-113">Utilizzare i valori di <xref:System.Windows.SystemParameters> nel codice, non è necessario utilizzare riferimenti statici o riferimenti a risorse dinamiche.</span><span class="sxs-lookup"><span data-stu-id="50426-113">To use the values of <xref:System.Windows.SystemParameters> in code, you do not have to use either static references or dynamic resource references.</span></span> <span data-ttu-id="50426-114">Utilizzare invece i valori del <xref:System.Windows.SystemParameters> classe.</span><span class="sxs-lookup"><span data-stu-id="50426-114">Instead, use the values of the <xref:System.Windows.SystemParameters> class.</span></span> <span data-ttu-id="50426-115">Anche se le proprietà non chiave sono apparentemente definite come proprietà statiche, il comportamento di runtime [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come ospitata dal sistema verranno rivaluterà le proprietà in tempo reale e risponderà correttamente eseguita dall'utente. le modifiche ai valori di sistema.</span><span class="sxs-lookup"><span data-stu-id="50426-115">Although the non-key properties are apparently defined as static properties, the runtime behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in realtime, and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="50426-116">Nell'esempio seguente viene illustrato come impostare la larghezza e altezza di un pulsante utilizzando <xref:System.Windows.SystemParameters> valori.</span><span class="sxs-lookup"><span data-stu-id="50426-116">The following example shows how to set the width and height of a button by using <xref:System.Windows.SystemParameters> values.</span></span>  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="50426-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50426-117">See Also</span></span>  
 <xref:System.Windows.SystemParameters>  
 [<span data-ttu-id="50426-118">Disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="50426-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="50426-119">Utilizzare la classe SystemFonts</span><span class="sxs-lookup"><span data-stu-id="50426-119">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="50426-120">Usare chiavi dei parametri di sistema</span><span class="sxs-lookup"><span data-stu-id="50426-120">Use System Parameters Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [<span data-ttu-id="50426-121">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="50426-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
