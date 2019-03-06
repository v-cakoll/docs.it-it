---
title: 'Procedura: Utilizzare la classe SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 5ed44da316ddee5ea3a83262f913da571bf75276
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378899"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="3576d-102">Procedura: Utilizzare la classe SystemFonts</span><span class="sxs-lookup"><span data-stu-id="3576d-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="3576d-103">Questo esempio illustra come usare le risorse statiche del <xref:System.Windows.SystemFonts> classe per poter applicare uno stile a un pulsante o personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="3576d-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3576d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3576d-104">Example</span></span>  
 <span data-ttu-id="3576d-105">Le risorse di sistema espongono diversi valori determinati dal sistema come risorse e proprietà per consentire la creazione di oggetti visivi coerenti con le impostazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="3576d-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="3576d-106"><xref:System.Windows.SystemFonts> è una classe che contiene entrambi i valori del tipo di carattere di sistema come proprietà statiche e proprietà che fanno riferimento le chiavi di risorsa che possono essere utilizzate per accedere a tali valori in modo dinamico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3576d-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="3576d-107">Ad esempio, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> è un <xref:System.Windows.SystemFonts> valore, e <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> è una chiave di risorsa corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3576d-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="3576d-108">Nelle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile usare i membri di <xref:System.Windows.SystemFonts> come proprietà statiche o riferimenti a risorse dinamiche (con il valore della proprietà statica come chiave).</span><span class="sxs-lookup"><span data-stu-id="3576d-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="3576d-109">Usare un riferimento alla risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare un riferimento a un valore statico.</span><span class="sxs-lookup"><span data-stu-id="3576d-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3576d-110">Nelle chiavi di risorsa il suffisso "Key" viene aggiunto al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="3576d-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="3576d-111">Nell'esempio seguente viene illustrato come accedere e usare le proprietà di <xref:System.Windows.SystemFonts> come valori statici per applicare uno stile a un pulsante o personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="3576d-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="3576d-112">Questo esempio di markup assegna <xref:System.Windows.SystemFonts> valori a un pulsante.</span><span class="sxs-lookup"><span data-stu-id="3576d-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="3576d-113">Per usare i valori di <xref:System.Windows.SystemFonts> nel codice, non è necessario utilizzare un valore statico o un riferimento di risorsa dinamica.</span><span class="sxs-lookup"><span data-stu-id="3576d-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="3576d-114">In alternativa, usare le proprietà non chiave della <xref:System.Windows.SystemFonts> classe.</span><span class="sxs-lookup"><span data-stu-id="3576d-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="3576d-115">Anche se le proprietà non chiave sono apparentemente definite come proprietà statiche, il comportamento di runtime di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitato dal sistema rivaluterà le proprietà in tempo reale e risponderà correttamente per le modifiche dall'utente ai valori di sistema.</span><span class="sxs-lookup"><span data-stu-id="3576d-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="3576d-116">L'esempio seguente illustra come specificare le impostazioni del tipo di carattere di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="3576d-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="3576d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3576d-117">See also</span></span>
- <xref:System.Windows.SystemFonts>
- [<span data-ttu-id="3576d-118">Disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="3576d-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="3576d-119">Utilizzare SystemParameters</span><span class="sxs-lookup"><span data-stu-id="3576d-119">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="3576d-120">Usare chiavi di caratteri del sistema</span><span class="sxs-lookup"><span data-stu-id="3576d-120">Use System Fonts Keys</span></span>](how-to-use-system-fonts-keys.md)
- [<span data-ttu-id="3576d-121">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="3576d-121">How-to Topics</span></span>](resources-how-to-topics.md)
- [<span data-ttu-id="3576d-122">Estensione del markup x:Static</span><span class="sxs-lookup"><span data-stu-id="3576d-122">x:Static Markup Extension</span></span>](../../xaml-services/x-static-markup-extension.md)
- [<span data-ttu-id="3576d-123">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="3576d-123">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="3576d-124">Estensione del markup DynamicResource</span><span class="sxs-lookup"><span data-stu-id="3576d-124">DynamicResource Markup Extension</span></span>](dynamicresource-markup-extension.md)
