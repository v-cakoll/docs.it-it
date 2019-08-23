---
title: 'Procedura: Usare la classe SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 7438705a82faee464649b5f6f577627a379e9a8c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918354"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="773d2-102">Procedura: Usare la classe SystemFonts</span><span class="sxs-lookup"><span data-stu-id="773d2-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="773d2-103">Questo esempio illustra come usare le risorse statiche della <xref:System.Windows.SystemFonts> classe per applicare uno stile a un pulsante o personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="773d2-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="773d2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="773d2-104">Example</span></span>  
 <span data-ttu-id="773d2-105">Le risorse di sistema espongono diversi valori determinati dal sistema come risorse e proprietà per consentire la creazione di oggetti visivi coerenti con le impostazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="773d2-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="773d2-106"><xref:System.Windows.SystemFonts>è una classe che contiene sia i valori dei tipi di carattere di sistema come proprietà statiche che le proprietà che fanno riferimento a chiavi di risorsa che possono essere usate per accedere dinamicamente a tali valori in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="773d2-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="773d2-107">Ad esempio, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> è un <xref:System.Windows.SystemFonts> valore e <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> è una chiave di risorsa corrispondente.</span><span class="sxs-lookup"><span data-stu-id="773d2-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="773d2-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]è possibile usare i membri di <xref:System.Windows.SystemFonts> come proprietà statiche o riferimenti a risorse dinamiche (con il valore della proprietà statica come chiave).</span><span class="sxs-lookup"><span data-stu-id="773d2-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="773d2-109">Usare un riferimento alla risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare un riferimento a un valore statico.</span><span class="sxs-lookup"><span data-stu-id="773d2-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="773d2-110">Nelle chiavi di risorsa il suffisso "Key" viene aggiunto al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="773d2-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="773d2-111">Nell'esempio seguente viene illustrato come accedere e utilizzare le proprietà di <xref:System.Windows.SystemFonts> come valori statici per applicare uno stile a un pulsante o personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="773d2-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="773d2-112">Questo esempio di markup assegna <xref:System.Windows.SystemFonts> i valori a un pulsante.</span><span class="sxs-lookup"><span data-stu-id="773d2-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="773d2-113">Per usare i valori di <xref:System.Windows.SystemFonts> nel codice, non è necessario usare un valore statico o un riferimento a una risorsa dinamica.</span><span class="sxs-lookup"><span data-stu-id="773d2-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="773d2-114">Usare invece le proprietà non chiave della <xref:System.Windows.SystemFonts> classe.</span><span class="sxs-lookup"><span data-stu-id="773d2-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="773d2-115">Anche se le proprietà non chiave sono apparentemente definite come proprietà statiche, il comportamento in fase di esecuzione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di ospitato dal sistema rivaluterà le proprietà in tempo reale e configurerà correttamente le modifiche guidate dall'utente ai valori di sistema.</span><span class="sxs-lookup"><span data-stu-id="773d2-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="773d2-116">L'esempio seguente illustra come specificare le impostazioni del tipo di carattere di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="773d2-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="773d2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="773d2-117">See also</span></span>

- <xref:System.Windows.SystemFonts>
- [<span data-ttu-id="773d2-118">Disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="773d2-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="773d2-119">Utilizzare SystemParameters</span><span class="sxs-lookup"><span data-stu-id="773d2-119">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="773d2-120">Usare chiavi di caratteri del sistema</span><span class="sxs-lookup"><span data-stu-id="773d2-120">Use System Fonts Keys</span></span>](how-to-use-system-fonts-keys.md)
- [<span data-ttu-id="773d2-121">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="773d2-121">How-to Topics</span></span>](resources-how-to-topics.md)
- [<span data-ttu-id="773d2-122">Estensione del markup x:Static</span><span class="sxs-lookup"><span data-stu-id="773d2-122">x:Static Markup Extension</span></span>](../../xaml-services/x-static-markup-extension.md)
- [<span data-ttu-id="773d2-123">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="773d2-123">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="773d2-124">Estensione del markup DynamicResource</span><span class="sxs-lookup"><span data-stu-id="773d2-124">DynamicResource Markup Extension</span></span>](dynamicresource-markup-extension.md)
