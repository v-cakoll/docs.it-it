---
title: Gestione di xml:lang in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b5a06adbb7cb874bc09899118f13b91fbec7a85e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071444"
---
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="e0757-102">Gestione di xml:lang in XAML</span><span class="sxs-lookup"><span data-stu-id="e0757-102">xml:lang Handling in XAML</span></span>

<span data-ttu-id="e0757-103">L'attributo `xml:lang` è un attributo definito in XML che dichiara le informazioni sulla lingua e sulle impostazioni cultura per un elemento in XML.</span><span class="sxs-lookup"><span data-stu-id="e0757-103">The `xml:lang` attribute is an XML-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="e0757-104">Il significato dell'attributo rimane persistente in XAML. Tuttavia, sono valide alcune considerazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e0757-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="e0757-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="e0757-105">XAML Attribute Usage</span></span>

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a><span data-ttu-id="e0757-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="e0757-106">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="e0757-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="e0757-107">*rfc3066lang*</span></span>|<span data-ttu-id="e0757-108">Stringa derivata dallo standard [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) che identifica una lingua o un'area linguistica.</span><span class="sxs-lookup"><span data-stu-id="e0757-108">A string that is derived from the [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="e0757-109">Se identifica un'area linguistica, la lingua e l'area sono separate da un trattino.</span><span class="sxs-lookup"><span data-stu-id="e0757-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="e0757-110">Per altre informazioni su valori e formato, vedere <xref:System.Windows.Markup.XmlLanguage> .</span><span class="sxs-lookup"><span data-stu-id="e0757-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e0757-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e0757-111">Remarks</span></span>

<span data-ttu-id="e0757-112">La definizione `xml:lang` per [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] l'attributo in deriva da `xml:lang` come definito come "attributo speciale" dal World Wide Web Consortium (W3C) per XML.</span><span class="sxs-lookup"><span data-stu-id="e0757-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the World Wide Web Consortium (W3C) for XML.</span></span> <span data-ttu-id="e0757-113">Le informazioni su lingua e cultura sono potenzialmente elaborate in modi diversi in base agli elementi, a seconda delle relative implementazioni. Tuttavia, non esiste alcuna elaborazione [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] predefinita dell'attributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="e0757-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>

<span data-ttu-id="e0757-114">Il valore predefinito dell'attributo `xml:lang` è una stringa vuota a livello di attributo.</span><span class="sxs-lookup"><span data-stu-id="e0757-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>

<span data-ttu-id="e0757-115">Gli effetti e il valore dell'attributo `xml:lang` vengono in genere trasferiti agli elementi figlio, quando vengono interpretati da sistemi che usano i valori `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="e0757-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>

<span data-ttu-id="e0757-116">Quando interpretato dai writer XAML dei `xml:lang` servizi <xref:System.Windows.Markup.XmlLanguage> XAML <xref:System.Globalization.CultureInfo> .NET, un valore può creare o oggetti nella rappresentazione dell'oggetto sottostante; Tuttavia, tale comportamento dipende dal `xml:lang` fatto che il valore specificato per sia una costruzione valida per tali classi.</span><span class="sxs-lookup"><span data-stu-id="e0757-116">When interpreted by XAML writers of .NET XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>

<span data-ttu-id="e0757-117">I framework possono creare associazioni tra le proprietà definite dal framework e il significato di `xml:lang` in XML mediante l'applicazione di <xref:System.Windows.Markup.XmlLangPropertyAttribute> alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="e0757-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>

## <a name="wpf-usage-nodes"></a><span data-ttu-id="e0757-118">Nodi di uso di WPF</span><span class="sxs-lookup"><span data-stu-id="e0757-118">WPF Usage Nodes</span></span>

<span data-ttu-id="e0757-119">Per gli elementi che sono classi derivate di <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, è possibile usare l'equivalente proprietà di dipendenza <xref:System.Windows.FrameworkElement.Language%2A> anziché l'attributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="e0757-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="e0757-120">Per impostazione predefinita, la proprietà <xref:System.Windows.FrameworkElement.Language%2A> usa "en-US" se non viene specificato un valore diverso tramite la proprietà o tramite l'elaborazione dell'attributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="e0757-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0757-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0757-121">See also</span></span>

- [<span data-ttu-id="e0757-122">Globalizzazione per WPF</span><span class="sxs-lookup"><span data-stu-id="e0757-122">Globalization for WPF</span></span>](../../framework/wpf/advanced/globalization-for-wpf.md)
