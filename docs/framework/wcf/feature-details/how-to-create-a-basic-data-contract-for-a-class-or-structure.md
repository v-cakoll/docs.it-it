---
title: 'Procedura: creare un contratto dati di base per una classe o una struttura'
description: Seguire questo esempio per informazioni su come creare un contratto dati usando una classe o una struttura in WCF usando l'attributo DataContractAttribute.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: a45fde58795947c3e46fa45750ae1a3faddd8849
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247169"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="d9da2-103">Procedura: creare un contratto dati di base per una classe o una struttura</span><span class="sxs-lookup"><span data-stu-id="d9da2-103">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="d9da2-104">In questo argomento vengono illustrati i passaggi di base per creare un contratto dati usando una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="d9da2-104">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="d9da2-105">Per ulteriori informazioni sui contratti dati e sul relativo utilizzo, vedere [Using Data Contracts](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="d9da2-105">For more information about data contracts and how they are used, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="d9da2-106">Per un'esercitazione che illustra i passaggi per la creazione di un servizio e di un client di base Windows Communication Foundation (WCF), vedere l' [esercitazione Introduzione](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d9da2-106">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="d9da2-107">Per un'applicazione di esempio funzionante costituita da un servizio e un client di base, vedere [contratto dati di base](../samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="d9da2-107">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="d9da2-108">Per creare un contratto dati di base per una classe o una struttura</span><span class="sxs-lookup"><span data-stu-id="d9da2-108">To create a basic data contract for a class or structure</span></span>  
  
1. <span data-ttu-id="d9da2-109">Dichiarare che il tipo è associato a un contratto dati applicando l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> alla classe.</span><span class="sxs-lookup"><span data-stu-id="d9da2-109">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="d9da2-110">Si noti che tutti i tipi pubblici, inclusi quelli senza attributi, sono serializzabili.</span><span class="sxs-lookup"><span data-stu-id="d9da2-110">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="d9da2-111">Tramite <xref:System.Runtime.Serialization.DataContractSerializer> viene dedotto un contratto dati se è assente l'attributo <xref:System.Runtime.Serialization.DataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d9da2-111">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="d9da2-112">Per ulteriori informazioni, vedere [tipi serializzabili](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="d9da2-112">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
2. <span data-ttu-id="d9da2-113">Definire i membri (proprietà, campi o eventi) serializzati applicando l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a ogni membro.</span><span class="sxs-lookup"><span data-stu-id="d9da2-113">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="d9da2-114">Questi membri vengono definiti membri dati.</span><span class="sxs-lookup"><span data-stu-id="d9da2-114">These members are called data members.</span></span> <span data-ttu-id="d9da2-115">Per impostazione predefinita, tutti i tipi pubblici sono serializzabili.</span><span class="sxs-lookup"><span data-stu-id="d9da2-115">By default, all public types are serializable.</span></span> <span data-ttu-id="d9da2-116">Per ulteriori informazioni, vedere [tipi serializzabili](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="d9da2-116">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d9da2-117">È possibile applicare l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> ai campi privati, per esporre i dati ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="d9da2-117">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="d9da2-118">Assicurarsi che il membro non contenga dati riservati.</span><span class="sxs-lookup"><span data-stu-id="d9da2-118">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9da2-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9da2-119">Example</span></span>  
 <span data-ttu-id="d9da2-120">Nell'esempio seguente viene illustrato come creare un contratto dati per il tipo `Person` applicando gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> alla classe e ai relativi membri.</span><span class="sxs-lookup"><span data-stu-id="d9da2-120">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d9da2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9da2-121">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="d9da2-122">Using Data Contracts</span><span class="sxs-lookup"><span data-stu-id="d9da2-122">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="d9da2-123">Esercitazione Introduzione</span><span class="sxs-lookup"><span data-stu-id="d9da2-123">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="d9da2-124">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="d9da2-124">Getting Started</span></span>](../samples/getting-started-sample.md)
