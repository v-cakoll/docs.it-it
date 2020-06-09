---
title: Ordine dei membri dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 717d7014f4c4a56249ead0c839cf05f4f83a6f5f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593464"
---
# <a name="data-member-order"></a><span data-ttu-id="d9e60-102">Ordine dei membri dati</span><span class="sxs-lookup"><span data-stu-id="d9e60-102">Data Member Order</span></span>
<span data-ttu-id="d9e60-103">In alcune applicazioni, è utile conoscere l'ordine in cui i dati dei vari membri dati vengono inviati o si prevede che siano ricevuti (ad esempio l'ordine in cui i dati vengono visualizzati nell'XML serializzato).</span><span class="sxs-lookup"><span data-stu-id="d9e60-103">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="d9e60-104">Talvolta può essere necessario modificare tale ordine.</span><span class="sxs-lookup"><span data-stu-id="d9e60-104">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="d9e60-105">In questo argomento vengono illustrate le regole di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="d9e60-105">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="d9e60-106">Regole di base</span><span class="sxs-lookup"><span data-stu-id="d9e60-106">Basic Rules</span></span>  
 <span data-ttu-id="d9e60-107">Le regole di base per l'ordinamento dei dati sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9e60-107">The basic rules for data ordering include:</span></span>  
  
- <span data-ttu-id="d9e60-108">Se un tipo di contratto dei dati fa parte di una gerarchia di ereditarietà, i membri dati dei relativi tipi di base sono sempre i primi dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="d9e60-108">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
- <span data-ttu-id="d9e60-109">Seguono in ordine alfabetico i membri dati del tipo corrente per i quali non è impostata la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> dell'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d9e60-109">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
- <span data-ttu-id="d9e60-110">Ci sono poi i membri dati per i quali è impostata la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> dell'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d9e60-110">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="d9e60-111">Questi vengono ordinati prima in base al valore della proprietà `Order` e quindi alfabeticamente in caso di presenza di più membri di un determinato valore `Order`.</span><span class="sxs-lookup"><span data-stu-id="d9e60-111">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="d9e60-112">I valori di ordinamento possono essere ignorati.</span><span class="sxs-lookup"><span data-stu-id="d9e60-112">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="d9e60-113">L'ordine alfabetico viene stabilito chiamando il metodo <xref:System.String.CompareOrdinal%2A>.</span><span class="sxs-lookup"><span data-stu-id="d9e60-113">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d9e60-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="d9e60-114">Examples</span></span>  
 <span data-ttu-id="d9e60-115">Si consideri il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d9e60-115">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="d9e60-116">L'XML prodotto è simile al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d9e60-116">The XML produced is similar to the following.</span></span>  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>
</DerivedType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9e60-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9e60-117">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [<span data-ttu-id="d9e60-118">Data Contract Equivalence</span><span class="sxs-lookup"><span data-stu-id="d9e60-118">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="d9e60-119">Using Data Contracts</span><span class="sxs-lookup"><span data-stu-id="d9e60-119">Using Data Contracts</span></span>](using-data-contracts.md)
