---
title: Gestione di coppie nome/valore (C#)
description: LINQ to XML contiene metodi che semplificano la gestione delle coppie nome/valore, sia come attributi che come set di elementi figlio.
ms.date: 07/20/2015
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 92a45d160cbb1ef470d93bf740d0b6f584681e72
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165275"
---
# <a name="maintaining-namevalue-pairs-c"></a><span data-ttu-id="2102d-103">Gestione di coppie nome/valore (C#)</span><span class="sxs-lookup"><span data-stu-id="2102d-103">Maintaining Name/Value Pairs (C#)</span></span>
<span data-ttu-id="2102d-104">In molte applicazioni è necessario gestire informazioni che è preferibile mantenere come coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="2102d-104">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="2102d-105">Queste informazioni potrebbero essere di configurazione o impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="2102d-105">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="2102d-106">include alcuni metodi che consentono di mantenere facilmente coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="2102d-106">contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="2102d-107">È possibile mantenere le informazioni come attributi o come un set di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="2102d-107">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="2102d-108">Una differenza tra il mantenere le informazioni come attributi o come elementi figlio è che gli attributi prevedono un vincolo in base al quale per un elemento può esistere un unico attributo con un nome specifico.</span><span class="sxs-lookup"><span data-stu-id="2102d-108">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="2102d-109">Questa limitazione non si applica invece agli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="2102d-109">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="2102d-110">SetAttributeValue e SetElementValue</span><span class="sxs-lookup"><span data-stu-id="2102d-110">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="2102d-111">I due metodi che facilitano il mantenimento delle coppie nome/valore sono <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> e <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="2102d-111">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="2102d-112">Si tratta di metodi contraddistinti da una semantica simile.</span><span class="sxs-lookup"><span data-stu-id="2102d-112">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="2102d-113"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> può aggiungere, modificare o rimuovere attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="2102d-113"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
- <span data-ttu-id="2102d-114">Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo non esistente, il metodo crea un nuovo attributo e lo aggiunge all'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="2102d-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="2102d-115">Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo esistente e contenuto specificato, il contenuto dell'attributo viene sostituito con quello specificato.</span><span class="sxs-lookup"><span data-stu-id="2102d-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="2102d-116">Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo esistente e si specifica null per il contenuto, l'attributo viene rimosso dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="2102d-116">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="2102d-117"><xref:System.Xml.Linq.XElement.SetElementValue%2A> può aggiungere, modificare o rimuovere elementi figlio di un elemento.</span><span class="sxs-lookup"><span data-stu-id="2102d-117"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
- <span data-ttu-id="2102d-118">Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento figlio non esistente, il metodo crea un nuovo elemento e lo aggiunge all'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="2102d-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="2102d-119">Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento esistente e contenuto specificato, il contenuto dell'elemento viene sostituito con quello specificato.</span><span class="sxs-lookup"><span data-stu-id="2102d-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="2102d-120">Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento esistente e si specifica null per il contenuto, l'elemento viene rimosso dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="2102d-120">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2102d-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="2102d-121">Example</span></span>  
 <span data-ttu-id="2102d-122">Nell'esempio seguente viene creato un elemento senza attributi.</span><span class="sxs-lookup"><span data-stu-id="2102d-122">The following example creates an element with no attributes.</span></span> <span data-ttu-id="2102d-123">Viene quindi usato il metodo <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> per creare e gestire un elenco di coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="2102d-123">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="2102d-124">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="2102d-124">This example produces the following output:</span></span>  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="2102d-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="2102d-125">Example</span></span>  
 <span data-ttu-id="2102d-126">Nell'esempio seguente viene creato un elemento senza elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="2102d-126">The following example creates an element with no child elements.</span></span> <span data-ttu-id="2102d-127">Viene quindi usato il metodo <xref:System.Xml.Linq.XElement.SetElementValue%2A> per creare e gestire un elenco di coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="2102d-127">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="2102d-128">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="2102d-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2102d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2102d-129">See also</span></span>

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [<span data-ttu-id="2102d-130">Modifica degli alberi XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2102d-130">Modifying XML Trees (LINQ to XML) (C#)</span></span>](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)
