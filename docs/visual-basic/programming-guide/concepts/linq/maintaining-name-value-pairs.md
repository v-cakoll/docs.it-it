---
title: Gestione di coppie nome/valore
ms.date: 07/20/2015
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
ms.openlocfilehash: b8c9487330239e7e6365055d5f08a02f2dbb0e37
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796145"
---
# <a name="maintaining-namevalue-pairs-visual-basic"></a><span data-ttu-id="c3266-102">Gestione delle coppie nome/valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3266-102">Maintaining Name/Value Pairs (Visual Basic)</span></span>
<span data-ttu-id="c3266-103">In molte applicazioni è necessario gestire informazioni che è preferibile mantenere come coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="c3266-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="c3266-104">Queste informazioni potrebbero essere di configurazione o impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="c3266-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="c3266-105">include alcuni metodi che consentono di mantenere facilmente coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="c3266-105">contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="c3266-106">È possibile mantenere le informazioni come attributi o come un set di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="c3266-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="c3266-107">Una differenza tra il mantenere le informazioni come attributi o come elementi figlio è che gli attributi prevedono un vincolo in base al quale per un elemento può esistere un unico attributo con un nome specifico.</span><span class="sxs-lookup"><span data-stu-id="c3266-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="c3266-108">Questa limitazione non si applica invece agli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="c3266-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="c3266-109">SetAttributeValue e SetElementValue</span><span class="sxs-lookup"><span data-stu-id="c3266-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="c3266-110">I due metodi che facilitano il mantenimento delle coppie nome/valore sono <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> e <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="c3266-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="c3266-111">Si tratta di metodi contraddistinti da una semantica simile.</span><span class="sxs-lookup"><span data-stu-id="c3266-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="c3266-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> può aggiungere, modificare o rimuovere attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="c3266-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
- <span data-ttu-id="c3266-113">Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo non esistente, il metodo crea un nuovo attributo e lo aggiunge all'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="c3266-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="c3266-114">Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo esistente e contenuto specificato, il contenuto dell'attributo viene sostituito con quello specificato.</span><span class="sxs-lookup"><span data-stu-id="c3266-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="c3266-115">Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo esistente e si specifica null per il contenuto, l'attributo viene rimosso dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="c3266-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="c3266-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> può aggiungere, modificare o rimuovere elementi figlio di un elemento.</span><span class="sxs-lookup"><span data-stu-id="c3266-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
- <span data-ttu-id="c3266-117">Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento figlio non esistente, il metodo crea un nuovo elemento e lo aggiunge all'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="c3266-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="c3266-118">Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento esistente e contenuto specificato, il contenuto dell'elemento viene sostituito con quello specificato.</span><span class="sxs-lookup"><span data-stu-id="c3266-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="c3266-119">Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento esistente e si specifica null per il contenuto, l'elemento viene rimosso dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="c3266-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3266-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3266-120">Example</span></span>  
 <span data-ttu-id="c3266-121">Nell'esempio seguente viene creato un elemento senza attributi.</span><span class="sxs-lookup"><span data-stu-id="c3266-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="c3266-122">Viene quindi usato il metodo <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> per creare e gestire un elenco di coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="c3266-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="c3266-123">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="c3266-123">This example produces the following output:</span></span>  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="c3266-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3266-124">Example</span></span>  
 <span data-ttu-id="c3266-125">Nell'esempio seguente viene creato un elemento senza elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="c3266-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="c3266-126">Viene quindi usato il metodo <xref:System.Xml.Linq.XElement.SetElementValue%2A> per creare e gestire un elenco di coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="c3266-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="c3266-127">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="c3266-127">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c3266-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3266-128">See also</span></span>

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [<span data-ttu-id="c3266-129">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3266-129">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
