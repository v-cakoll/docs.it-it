---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: 2e2e36486c3788cd714ffd0ed545fbb14f831476
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373673"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="3aa87-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="3aa87-102">ReliableSessionBindingElement</span></span>
<span data-ttu-id="3aa87-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="3aa87-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa87-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3aa87-104">Syntax</span></span>  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3aa87-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3aa87-105">Methods</span></span>  
 <span data-ttu-id="3aa87-106">La classe ReliableSessionBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="3aa87-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3aa87-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3aa87-107">Properties</span></span>  
 <span data-ttu-id="3aa87-108">La classe ReliableSessionBindingElement ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa87-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="3aa87-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="3aa87-109">AcknowledgementInterval</span></span>  
 <span data-ttu-id="3aa87-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="3aa87-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="3aa87-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa87-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa87-112">Intervallo di tempo che una destinazione attende prima di inviare un acknowledgment all'origine del messaggio sui canali affidabili creati dalla factory.</span><span class="sxs-lookup"><span data-stu-id="3aa87-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="3aa87-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="3aa87-113">FlowControlEnabled</span></span>  
 <span data-ttu-id="3aa87-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="3aa87-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="3aa87-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa87-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa87-116">Valore booleano che specifica se è attivato il controllo di flusso.</span><span class="sxs-lookup"><span data-stu-id="3aa87-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="3aa87-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="3aa87-117">InactivityTimeout</span></span>  
 <span data-ttu-id="3aa87-118">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="3aa87-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="3aa87-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa87-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa87-120">Specifica il limite massimo di tempo per cui il canale consente all'altra parte della comunicazione di non inviare messaggi prima di generare un errore per il canale.</span><span class="sxs-lookup"><span data-stu-id="3aa87-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="3aa87-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="3aa87-121">MaxPendingChannels</span></span>  
 <span data-ttu-id="3aa87-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3aa87-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="3aa87-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa87-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa87-124">Numero massimo di canali che possono attendere nel listener prima di essere accettati.</span><span class="sxs-lookup"><span data-stu-id="3aa87-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="3aa87-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="3aa87-125">MaxRetryCount</span></span>  
 <span data-ttu-id="3aa87-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3aa87-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="3aa87-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa87-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa87-128">Numero massimo di tentativi di ritrasmissione di un messaggio per cui un canale affidabile non ha ricevuto un acknowledgment, tramite una chiamata a `Send` sul canale sottostante.</span><span class="sxs-lookup"><span data-stu-id="3aa87-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="3aa87-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="3aa87-129">MaxTransferWindowSize</span></span>  
 <span data-ttu-id="3aa87-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3aa87-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="3aa87-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa87-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa87-132">Dimensione massima della finestra di trasferimento per la sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="3aa87-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="3aa87-133">Ordered</span><span class="sxs-lookup"><span data-stu-id="3aa87-133">Ordered</span></span>  
 <span data-ttu-id="3aa87-134">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="3aa87-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="3aa87-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa87-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa87-136">Valore booleano che specifica se è garantito l'arrivo dei messaggi nell'ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="3aa87-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="3aa87-137">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="3aa87-137">ReliableMessagingVersion</span></span>  
 <span data-ttu-id="3aa87-138">Tipo di dati: numero intero</span><span class="sxs-lookup"><span data-stu-id="3aa87-138">Data type: integer</span></span>  
  
 <span data-ttu-id="3aa87-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa87-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa87-140">Numero intero che specifica la versione del protocollo WS-ReliableMessaging usata nella sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="3aa87-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa87-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3aa87-141">Requirements</span></span>  
  
|<span data-ttu-id="3aa87-142">MOF</span><span class="sxs-lookup"><span data-stu-id="3aa87-142">MOF</span></span>|<span data-ttu-id="3aa87-143">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3aa87-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3aa87-144">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3aa87-144">Namespace</span></span>|<span data-ttu-id="3aa87-145">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3aa87-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3aa87-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aa87-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
