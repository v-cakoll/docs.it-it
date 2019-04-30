---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962956"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="41bac-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="41bac-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="41bac-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="41bac-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41bac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41bac-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="41bac-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="41bac-105">Methods</span></span>  
 <span data-ttu-id="41bac-106">La classe PeerTransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="41bac-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="41bac-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="41bac-107">Properties</span></span>  
 <span data-ttu-id="41bac-108">La classe PeerTransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="41bac-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="41bac-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="41bac-109">ListenIPAddress</span></span>  
 <span data-ttu-id="41bac-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="41bac-110">Data type: string</span></span>  
  
 <span data-ttu-id="41bac-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="41bac-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="41bac-112">Indirizzo IP su cui il nodo del peer è in attesa di messaggi.</span><span class="sxs-lookup"><span data-stu-id="41bac-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="41bac-113">Porta</span><span class="sxs-lookup"><span data-stu-id="41bac-113">Port</span></span>  
 <span data-ttu-id="41bac-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="41bac-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="41bac-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="41bac-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="41bac-116">Porta di interfaccia di rete su cui l'associazione elabora messaggi del canale del peer.</span><span class="sxs-lookup"><span data-stu-id="41bac-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="41bac-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="41bac-117">Security</span></span>  
 <span data-ttu-id="41bac-118">Tipo di dati: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="41bac-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="41bac-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="41bac-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="41bac-120">Impostazioni di sicurezza del trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="41bac-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41bac-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41bac-121">Requirements</span></span>  
  
|<span data-ttu-id="41bac-122">MOF</span><span class="sxs-lookup"><span data-stu-id="41bac-122">MOF</span></span>|<span data-ttu-id="41bac-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="41bac-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="41bac-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="41bac-124">Namespace</span></span>|<span data-ttu-id="41bac-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="41bac-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41bac-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41bac-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
