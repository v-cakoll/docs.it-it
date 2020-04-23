---
title: '{}Sequenza di escape - Estensione di markup'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071745"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="fcf5c-102">{}Sequenza di escape / estensione di markup</span><span class="sxs-lookup"><span data-stu-id="fcf5c-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="fcf5c-103">Fornisce la sequenza di escape XAML per i valori degli attributi.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="fcf5c-104">La sequenza di escape consente ai valori successivi nell'attributo di essere interpretati come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="fcf5c-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="fcf5c-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="fcf5c-106">Utilizzo della sintassi XAML per elementi proprietà</span><span class="sxs-lookup"><span data-stu-id="fcf5c-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="fcf5c-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="fcf5c-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="fcf5c-108">*valore letteraleValore*</span><span class="sxs-lookup"><span data-stu-id="fcf5c-108">*literalValue*</span></span>|<span data-ttu-id="fcf5c-109">Stringa letterale che segue la sequenza di escape.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="fcf5c-110">In genere questa stringa contiene una parentesi graffa aperta o chiusa (Sezione o ) .</span><span class="sxs-lookup"><span data-stu-id="fcf5c-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="fcf5c-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fcf5c-111">Remarks</span></span>

<span data-ttu-id="fcf5c-112">La sequenza{}di escape ( ) viene utilizzata in modo che sia possibile utilizzare una parentesi graffa aperta ( ) come carattere letterale in XAML.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="fcf5c-113">I lettori XAML usano in genere la parentesi graffa aperta per indicare il punto di ingresso di un'estensione di markup; tuttavia, controllano innanzitutto il carattere successivo per determinare se si tratta di una parentesi graffa di chiusura ().</span><span class="sxs-lookup"><span data-stu-id="fcf5c-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="fcf5c-114">Solo quando le due{}parentesi graffe ( ) sono adiacenti, vengono considerate una sequenza di escape.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="fcf5c-115">Se viene rilevata la sequenza di escape, il reader XAML deve elaborare il resto della stringa come stringa.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="fcf5c-116">Tuttavia, se la sequenza di escape viene applicata a un membro che dispone di un convertitore di tipi, la stringa potrebbe subire la conversione del tipo quando viene interpretata da un writer XAML.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="fcf5c-117">La sequenza di escape non è un'estensione di markup e non è supportata da una classe.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="fcf5c-118">Tuttavia, è una convenzione che i lettori XAML (inclusi i reader XAML personalizzati) devono rispettare.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="fcf5c-119">Le virgolette (") non possono essere utilizzate come sequenza di escape in questo modo.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="fcf5c-120">Se è necessario impostare una virgoletta come valore di proprietà per una proprietà non di contenuto, utilizzare la sintassi degli elementi proprietà e inserire le virgolette come stringa all'interno dell'elemento proprietà oppure utilizzare un'entità carattere XML.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="fcf5c-121">Per una proprietà di contenuto, le virgolette possono essere l'intero contenuto.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="fcf5c-122">La sequenza{}di escape ( ) è spesso necessaria quando si specifica un tipo XML che deve includere un qualificatore dello spazio dei nomi in una posizione in cui potrebbe essere visualizzata un'estensione di markup XAML.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="fcf5c-123">Questa posizione include l'inizio di un valore dell'attributo XAML e in un'estensione di markup immediatamente dopo un segno di uguale (Sezione ).</span><span class="sxs-lookup"><span data-stu-id="fcf5c-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="fcf5c-124">Nell'esempio seguente vengono illustrate le sequenze di escape per uno spazio dei nomi XML visualizzato all'inizio di un valore di attributo XAML.</span><span class="sxs-lookup"><span data-stu-id="fcf5c-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="fcf5c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcf5c-125">See also</span></span>

- [<span data-ttu-id="fcf5c-126">Convertitori di tipi ed estensioni di markup per XAML</span><span class="sxs-lookup"><span data-stu-id="fcf5c-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="fcf5c-127">Entità carattere XML e XAML</span><span class="sxs-lookup"><span data-stu-id="fcf5c-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
