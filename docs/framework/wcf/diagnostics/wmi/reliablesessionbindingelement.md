---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: b0a621da43402777cc620f1876bd968a72bb8c12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962916"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="cede4-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="cede4-102">ReliableSessionBindingElement</span></span>
<span data-ttu-id="cede4-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="cede4-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cede4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cede4-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="cede4-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="cede4-105">Methods</span></span>  
 <span data-ttu-id="cede4-106">La classe ReliableSessionBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="cede4-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cede4-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cede4-107">Properties</span></span>  
 <span data-ttu-id="cede4-108">La classe ReliableSessionBindingElement ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="cede4-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="cede4-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="cede4-109">AcknowledgementInterval</span></span>  
 <span data-ttu-id="cede4-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="cede4-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="cede4-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cede4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cede4-112">Intervallo di tempo che una destinazione attende prima di inviare un acknowledgment all'origine del messaggio sui canali affidabili creati dalla factory.</span><span class="sxs-lookup"><span data-stu-id="cede4-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="cede4-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="cede4-113">FlowControlEnabled</span></span>  
 <span data-ttu-id="cede4-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="cede4-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="cede4-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cede4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cede4-116">Valore booleano che specifica se è attivato il controllo di flusso.</span><span class="sxs-lookup"><span data-stu-id="cede4-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="cede4-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="cede4-117">InactivityTimeout</span></span>  
 <span data-ttu-id="cede4-118">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="cede4-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="cede4-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cede4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cede4-120">Specifica il limite massimo di tempo per cui il canale consente all'altra parte della comunicazione di non inviare messaggi prima di generare un errore per il canale.</span><span class="sxs-lookup"><span data-stu-id="cede4-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="cede4-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="cede4-121">MaxPendingChannels</span></span>  
 <span data-ttu-id="cede4-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="cede4-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="cede4-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cede4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cede4-124">Numero massimo di canali che possono attendere nel listener prima di essere accettati.</span><span class="sxs-lookup"><span data-stu-id="cede4-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="cede4-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="cede4-125">MaxRetryCount</span></span>  
 <span data-ttu-id="cede4-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="cede4-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="cede4-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cede4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cede4-128">Numero massimo di tentativi di ritrasmissione di un messaggio per cui un canale affidabile non ha ricevuto un acknowledgment, tramite una chiamata a `Send` sul canale sottostante.</span><span class="sxs-lookup"><span data-stu-id="cede4-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="cede4-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="cede4-129">MaxTransferWindowSize</span></span>  
 <span data-ttu-id="cede4-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="cede4-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="cede4-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cede4-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cede4-132">Dimensione massima della finestra di trasferimento per la sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="cede4-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="cede4-133">Ordered</span><span class="sxs-lookup"><span data-stu-id="cede4-133">Ordered</span></span>  
 <span data-ttu-id="cede4-134">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="cede4-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="cede4-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cede4-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cede4-136">Valore booleano che specifica se è garantito l'arrivo dei messaggi nell'ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="cede4-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="cede4-137">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="cede4-137">ReliableMessagingVersion</span></span>  
 <span data-ttu-id="cede4-138">Tipo di dati: numero intero</span><span class="sxs-lookup"><span data-stu-id="cede4-138">Data type: integer</span></span>  
  
 <span data-ttu-id="cede4-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cede4-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cede4-140">Numero intero che specifica la versione del protocollo WS-ReliableMessaging usata nella sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="cede4-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cede4-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cede4-141">Requirements</span></span>  
  
|<span data-ttu-id="cede4-142">MOF</span><span class="sxs-lookup"><span data-stu-id="cede4-142">MOF</span></span>|<span data-ttu-id="cede4-143">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cede4-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cede4-144">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="cede4-144">Namespace</span></span>|<span data-ttu-id="cede4-145">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cede4-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cede4-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cede4-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
