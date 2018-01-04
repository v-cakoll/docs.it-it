---
title: Sequenza di escape {} - estensione di Markup
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: "21"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8419a1e89d5e94b9868b0fd1fb81540253efca5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="c50a5-102">Sequenza di escape/Estensione di markup {}</span><span class="sxs-lookup"><span data-stu-id="c50a5-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="c50a5-103">Fornisce la sequenza di escape XAML per i valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="c50a5-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="c50a5-104">La sequenza di escape consente i valori successivi nell'attributo deve essere interpretato come un valore letterale.</span><span class="sxs-lookup"><span data-stu-id="c50a5-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c50a5-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="c50a5-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="c50a5-106">Utilizzo della sintassi XAML per elementi proprietà</span><span class="sxs-lookup"><span data-stu-id="c50a5-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c50a5-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="c50a5-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c50a5-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="c50a5-108">*literalValue*</span></span>|<span data-ttu-id="c50a5-109">La stringa letterale che segue la sequenza di escape.</span><span class="sxs-lookup"><span data-stu-id="c50a5-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="c50a5-110">In genere questa stringa contiene una parentesi graffa aperta o chiusa ({o}).</span><span class="sxs-lookup"><span data-stu-id="c50a5-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c50a5-111">Note</span><span class="sxs-lookup"><span data-stu-id="c50a5-111">Remarks</span></span>  
 <span data-ttu-id="c50a5-112">La sequenza di escape ({}) viene utilizzata in modo che una parentesi graffa aperta ({}) può essere utilizzata come carattere letterale in XAML.</span><span class="sxs-lookup"><span data-stu-id="c50a5-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="c50a5-113">In genere, i reader XAML usano la parentesi graffa di apertura ({}) per indicare il punto di ingresso di un'estensione di markup; tuttavia, vengono innanzitutto controllare il carattere successivo per determinare se è una parentesi graffa di chiusura (}).</span><span class="sxs-lookup"><span data-stu-id="c50a5-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="c50a5-114">Solo quando le due parentesi graffe ({) sono adiacenti, vengono considerati una sequenza di escape.</span><span class="sxs-lookup"><span data-stu-id="c50a5-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="c50a5-115">Se la sequenza di escape viene rilevata, il reader XAML deve elaborare il resto della stringa come stringa.</span><span class="sxs-lookup"><span data-stu-id="c50a5-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="c50a5-116">Tuttavia, se la sequenza di escape viene applicata a un membro che dispone di un convertitore di tipi, la stringa potrebbe essere sottoposto a conversione del tipo quando questo viene interpretato da un writer XAML.</span><span class="sxs-lookup"><span data-stu-id="c50a5-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="c50a5-117">La sequenza di escape non è un'estensione di markup e non è supportata da una classe.</span><span class="sxs-lookup"><span data-stu-id="c50a5-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="c50a5-118">Tuttavia, è una convenzione che devono rispettare i reader XAML (inclusi i reader XAML personalizzati).</span><span class="sxs-lookup"><span data-stu-id="c50a5-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="c50a5-119">Un segno di virgolette (") può essere utilizzato come una sequenza di escape in questo modo.</span><span class="sxs-lookup"><span data-stu-id="c50a5-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="c50a5-120">Se è necessario impostare una virgoletta come valore della proprietà per una proprietà noncontent, utilizzare la sintassi degli elementi di proprietà e inserire le virgolette come una stringa all'interno dell'elemento di proprietà oppure utilizzare un'entità carattere XML.</span><span class="sxs-lookup"><span data-stu-id="c50a5-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="c50a5-121">Per una proprietà di contenuto, la virgoletta può essere l'intero contenuto.</span><span class="sxs-lookup"><span data-stu-id="c50a5-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="c50a5-122">La sequenza di escape ({}) è spesso necessaria quando si specifica un tipo XML che deve includere un qualificatore dello spazio dei nomi in un percorso in cui può essere presente un'estensione di markup XAML.</span><span class="sxs-lookup"><span data-stu-id="c50a5-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="c50a5-123">Ciò include l'inizio di un valore di attributo XAML in un'estensione di markup, immediatamente dopo il segno di uguale (=).</span><span class="sxs-lookup"><span data-stu-id="c50a5-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="c50a5-124">L'esempio seguente mostra le sequenze di escape per uno spazio dei nomi XML che viene visualizzato all'inizio di un valore di attributo XAML.</span><span class="sxs-lookup"><span data-stu-id="c50a5-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="c50a5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c50a5-125">See Also</span></span>  
 [<span data-ttu-id="c50a5-126">Convertitori di tipi ed estensioni di markup per XAML</span><span class="sxs-lookup"><span data-stu-id="c50a5-126">Type Converters and Markup Extensions for XAML</span></span>](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [<span data-ttu-id="c50a5-127">Entità carattere XML e XAML</span><span class="sxs-lookup"><span data-stu-id="c50a5-127">XML Character Entities and XAML</span></span>](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
