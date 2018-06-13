---
title: 'Procedura: creare un contratto dati di base per una classe o una struttura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: bb2cebabc8e51870398689ea032d27c72f0503b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490068"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="2df02-102">Procedura: creare un contratto dati di base per una classe o una struttura</span><span class="sxs-lookup"><span data-stu-id="2df02-102">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="2df02-103">In questo argomento vengono illustrati i passaggi di base per creare un contratto dati usando una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="2df02-103">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="2df02-104">Per ulteriori informazioni sui contratti dati e modalità di utilizzo, vedere [utilizzando i contratti dati](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="2df02-104">For more information about data contracts and how they are used, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="2df02-105">Per un'esercitazione che illustra in dettaglio i passaggi della creazione di un servizio Windows Communication Foundation (WCF) di base e un client, vedere la [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="2df02-105">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="2df02-106">Per un'applicazione di esempio funzionante che è costituito da un servizio di base e un client, vedere [base contratto dati](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="2df02-106">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="2df02-107">Per creare un contratto dati di base per una classe o una struttura</span><span class="sxs-lookup"><span data-stu-id="2df02-107">To create a basic data contract for a class or structure</span></span>  
  
1.  <span data-ttu-id="2df02-108">Dichiarare che il tipo è associato a un contratto dati applicando l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> alla classe.</span><span class="sxs-lookup"><span data-stu-id="2df02-108">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="2df02-109">Si noti che tutti i tipi pubblici, inclusi quelli senza attributi, sono serializzabili.</span><span class="sxs-lookup"><span data-stu-id="2df02-109">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="2df02-110">Tramite <xref:System.Runtime.Serialization.DataContractSerializer> viene dedotto un contratto dati se è assente l'attributo <xref:System.Runtime.Serialization.DataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2df02-110">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="2df02-111">Per altre informazioni, vedere [tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="2df02-111">For more information, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
2.  <span data-ttu-id="2df02-112">Definire i membri (proprietà, campi o eventi) serializzati applicando l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a ogni membro.</span><span class="sxs-lookup"><span data-stu-id="2df02-112">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="2df02-113">Questi membri vengono definiti membri dati.</span><span class="sxs-lookup"><span data-stu-id="2df02-113">These members are called data members.</span></span> <span data-ttu-id="2df02-114">Per impostazione predefinita, tutti i tipi pubblici sono serializzabili.</span><span class="sxs-lookup"><span data-stu-id="2df02-114">By default, all public types are serializable.</span></span> <span data-ttu-id="2df02-115">Per altre informazioni, vedere [tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="2df02-115">For more information, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2df02-116">È possibile applicare l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> ai campi privati, per esporre i dati ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="2df02-116">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="2df02-117">Assicurarsi che il membro non contenga dati riservati.</span><span class="sxs-lookup"><span data-stu-id="2df02-117">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2df02-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="2df02-118">Example</span></span>  
 <span data-ttu-id="2df02-119">Nell'esempio seguente viene illustrato come creare un contratto dati per il tipo `Person` applicando gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> alla classe e ai relativi membri.</span><span class="sxs-lookup"><span data-stu-id="2df02-119">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2df02-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2df02-120">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="2df02-121">Uso di contratti di dati</span><span class="sxs-lookup"><span data-stu-id="2df02-121">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="2df02-122">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="2df02-122">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="2df02-123">Introduzione</span><span class="sxs-lookup"><span data-stu-id="2df02-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
