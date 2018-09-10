---
title: 'File XML di esempio: dati numerici in uno spazio dei nomi3'
ms.date: 07/20/2015
ms.assetid: 51750cab-3c66-4511-90fb-b9d211308d31
ms.openlocfilehash: 114657087a0aee69bc9be298025eac58923294b0
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185610"
---
# <a name="sample-xml-file-numerical-data-in-a-namespace"></a><span data-ttu-id="27ae4-102">File XML di esempio: dati numerici in uno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="27ae4-102">Sample XML File: Numerical Data in a Namespace</span></span>
<span data-ttu-id="27ae4-103">Il file XML seguente viene usato in vari esempi nella documentazione di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27ae4-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="27ae4-104">Questo file contiene dati numerici per il calcolo della somma e della media, nonché per il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="27ae4-104">This file contains numerical data for summing, averaging, and grouping.</span></span> <span data-ttu-id="27ae4-105">L'XML si trova in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="27ae4-105">The XML is in a namespace.</span></span>  
  
## <a name="data"></a><span data-ttu-id="27ae4-106">Dati</span><span class="sxs-lookup"><span data-stu-id="27ae4-106">Data</span></span>  
  
```xml  
<Root xmlns='http://www.adatum.com'>  
  <TaxRate>7.25</TaxRate>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>24.50</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>1</Quantity>  
    <Price>89.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>5</Quantity>  
    <Price>4.95</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>66.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>10</Quantity>  
    <Price>.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>15</Quantity>  
    <Price>29.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>8</Quantity>  
    <Price>6.99</Price>  
  </Data>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27ae4-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27ae4-107">See Also</span></span>

- [<span data-ttu-id="27ae4-108">Documenti XML di esempio (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="27ae4-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
