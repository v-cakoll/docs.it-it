---
title: Ordine dei membri dati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06b311f0ca8e9b0a298cd1d9a5e87ff96d13a787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="data-member-order"></a><span data-ttu-id="f991d-102">Ordine dei membri dati</span><span class="sxs-lookup"><span data-stu-id="f991d-102">Data Member Order</span></span>
<span data-ttu-id="f991d-103">In alcune applicazioni, è utile conoscere l'ordine in cui i dati dei vari membri dati vengono inviati o si prevede che siano ricevuti (ad esempio l'ordine in cui i dati vengono visualizzati nell'XML serializzato).</span><span class="sxs-lookup"><span data-stu-id="f991d-103">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="f991d-104">Talvolta può essere necessario modificare tale ordine.</span><span class="sxs-lookup"><span data-stu-id="f991d-104">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="f991d-105">In questo argomento vengono illustrate le regole di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="f991d-105">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="f991d-106">Regole di base</span><span class="sxs-lookup"><span data-stu-id="f991d-106">Basic Rules</span></span>  
 <span data-ttu-id="f991d-107">Le regole di base per l'ordinamento dei dati sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f991d-107">The basic rules for data ordering include:</span></span>  
  
-   <span data-ttu-id="f991d-108">Se un tipo di contratto dei dati fa parte di una gerarchia di ereditarietà, i membri dati dei relativi tipi di base sono sempre i primi dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="f991d-108">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
-   <span data-ttu-id="f991d-109">Seguono in ordine alfabetico i membri dati del tipo corrente per i quali non è impostata la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> dell'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f991d-109">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
-   <span data-ttu-id="f991d-110">Ci sono poi i membri dati per i quali è impostata la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> dell'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f991d-110">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="f991d-111">Questi vengono ordinati prima in base al valore della proprietà `Order` e quindi alfabeticamente in caso di presenza di più membri di un determinato valore `Order`.</span><span class="sxs-lookup"><span data-stu-id="f991d-111">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="f991d-112">I valori di ordinamento possono essere ignorati.</span><span class="sxs-lookup"><span data-stu-id="f991d-112">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="f991d-113">L'ordine alfabetico viene stabilito chiamando il metodo <xref:System.String.CompareOrdinal%2A>.</span><span class="sxs-lookup"><span data-stu-id="f991d-113">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f991d-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="f991d-114">Examples</span></span>  
 <span data-ttu-id="f991d-115">Si consideri il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f991d-115">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="f991d-116">L'XML prodotto è simile al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f991d-116">The XML produced is similar to the following.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f991d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f991d-117">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 [<span data-ttu-id="f991d-118">Equivalenza dei contratti dati</span><span class="sxs-lookup"><span data-stu-id="f991d-118">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="f991d-119">Uso di contratti dati</span><span class="sxs-lookup"><span data-stu-id="f991d-119">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
