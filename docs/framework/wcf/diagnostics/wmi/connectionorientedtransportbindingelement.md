---
title: ConnectionOrientedTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0d399eb859118dfe94eb9e0a421fa405ae0f414
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="d9cf6-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d9cf6-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="d9cf6-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d9cf6-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9cf6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9cf6-104">Syntax</span></span>  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d9cf6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d9cf6-105">Methods</span></span>  
 <span data-ttu-id="d9cf6-106">La classe ConnectionOrientedTransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d9cf6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d9cf6-107">Properties</span></span>  
 <span data-ttu-id="d9cf6-108">La classe ConnectionOrientedTransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9cf6-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="d9cf6-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="d9cf6-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="d9cf6-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="d9cf6-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="d9cf6-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d9cf6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9cf6-112">TimeSpan che specifica l'intervallo di tempo per il completamento dell'inizializzazione del canale prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="d9cf6-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="d9cf6-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="d9cf6-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d9cf6-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="d9cf6-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d9cf6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9cf6-116">Dimensione del buffer usata per trasmettere un blocco del messaggio serializzato in transito dal client o servizio.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="d9cf6-117">HostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="d9cf6-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="d9cf6-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d9cf6-118">Data type: string</span></span>  
  
 <span data-ttu-id="d9cf6-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d9cf6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9cf6-120">Valore che indica se viene usato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="d9cf6-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="d9cf6-121">MaxBufferSize</span></span>  
 <span data-ttu-id="d9cf6-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d9cf6-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="d9cf6-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d9cf6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9cf6-124">Dimensione massima del buffer da usare.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="d9cf6-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="d9cf6-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="d9cf6-126">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="d9cf6-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="d9cf6-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d9cf6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9cf6-128">Intervallo di tempo massimo per cui un blocco di un messaggio o un messaggio intero può rimanere memorizzato nel buffer prima dell'invio.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="d9cf6-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="d9cf6-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="d9cf6-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d9cf6-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="d9cf6-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d9cf6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9cf6-132">Numero massimo di thread asincroni in sospeso disponibili per l'elaborazione delle connessioni in ingresso del servizio.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="d9cf6-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="d9cf6-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="d9cf6-134">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d9cf6-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="d9cf6-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d9cf6-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9cf6-136">Numero massimo di connessioni in sospeso.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="d9cf6-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="d9cf6-137">TransferMode</span></span>  
 <span data-ttu-id="d9cf6-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d9cf6-138">Data type: string</span></span>  
  
 <span data-ttu-id="d9cf6-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d9cf6-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9cf6-140">Valore che specifica se i messaggi vengono memorizzati nel buffer o trasmessi con il trasporto orientato alla connessione.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9cf6-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9cf6-141">Requirements</span></span>  
  
|<span data-ttu-id="d9cf6-142">MOF</span><span class="sxs-lookup"><span data-stu-id="d9cf6-142">MOF</span></span>|<span data-ttu-id="d9cf6-143">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d9cf6-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d9cf6-144">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d9cf6-144">Namespace</span></span>|<span data-ttu-id="d9cf6-145">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d9cf6-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9cf6-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9cf6-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
