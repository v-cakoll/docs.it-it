---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 572a19723583a6bc717a71b3b46040148f29e1cd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="6b592-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="6b592-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="6b592-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="6b592-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b592-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b592-104">Syntax</span></span>  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6b592-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="6b592-105">Methods</span></span>  
 <span data-ttu-id="6b592-106">La classe MsmqTransportBindingElement non definisce alcun metodo.</span><span class="sxs-lookup"><span data-stu-id="6b592-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6b592-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6b592-107">Properties</span></span>  
 <span data-ttu-id="6b592-108">La classe MsmqTransportBindingElement ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b592-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="6b592-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="6b592-109">MaxPoolSize</span></span>  
 <span data-ttu-id="6b592-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="6b592-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="6b592-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="6b592-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b592-112">Dimensione massima del pool che contiene oggetti di messaggi MSMQ interni.</span><span class="sxs-lookup"><span data-stu-id="6b592-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="6b592-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="6b592-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="6b592-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="6b592-114">Data type: string</span></span>  
  
 <span data-ttu-id="6b592-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="6b592-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b592-116">Valore di enumerazione che indica il trasporto per il canale delle comunicazioni in coda utilizzato da questa associazione.</span><span class="sxs-lookup"><span data-stu-id="6b592-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="6b592-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="6b592-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="6b592-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="6b592-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="6b592-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="6b592-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b592-120">Restituisce un valore booleano che indica se convertire gli indirizzi delle code mediante Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6b592-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b592-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b592-121">Requirements</span></span>  
  
|<span data-ttu-id="6b592-122">MOF</span><span class="sxs-lookup"><span data-stu-id="6b592-122">MOF</span></span>|<span data-ttu-id="6b592-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6b592-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6b592-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="6b592-124">Namespace</span></span>|<span data-ttu-id="6b592-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6b592-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b592-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b592-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
