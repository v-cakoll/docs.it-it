---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: dc7a29e5911a9d0a774e36f5be8c1f3cacad69b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486617"
---
# <a name="transportbindingelement"></a><span data-ttu-id="0dc9b-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0dc9b-102">TransportBindingElement</span></span>
<span data-ttu-id="0dc9b-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0dc9b-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0dc9b-104">Syntax</span></span>  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0dc9b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0dc9b-105">Methods</span></span>  
 <span data-ttu-id="0dc9b-106">La classe TransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="0dc9b-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0dc9b-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0dc9b-107">Properties</span></span>  
 <span data-ttu-id="0dc9b-108">La classe TransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dc9b-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="0dc9b-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="0dc9b-109">ManualAddressing</span></span>  
 <span data-ttu-id="0dc9b-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="0dc9b-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="0dc9b-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0dc9b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dc9b-112">Valore booleano che specifica se l'utente desidera controllare l'indirizzamento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="0dc9b-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="0dc9b-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="0dc9b-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="0dc9b-114">Tipo di dati: sint64</span><span class="sxs-lookup"><span data-stu-id="0dc9b-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="0dc9b-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0dc9b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dc9b-116">Dimensioni massime del pool di buffer dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="0dc9b-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="0dc9b-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="0dc9b-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="0dc9b-118">Tipo di dati: sint64</span><span class="sxs-lookup"><span data-stu-id="0dc9b-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="0dc9b-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0dc9b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dc9b-120">Dimensioni massime di un messaggio elaborato dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="0dc9b-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="0dc9b-121">Scheme</span><span class="sxs-lookup"><span data-stu-id="0dc9b-121">Scheme</span></span>  
 <span data-ttu-id="0dc9b-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0dc9b-122">Data type: string</span></span>  
  
 <span data-ttu-id="0dc9b-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0dc9b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dc9b-124">Schema URI del trasporto.</span><span class="sxs-lookup"><span data-stu-id="0dc9b-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dc9b-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0dc9b-125">Requirements</span></span>  
  
|<span data-ttu-id="0dc9b-126">MOF</span><span class="sxs-lookup"><span data-stu-id="0dc9b-126">MOF</span></span>|<span data-ttu-id="0dc9b-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0dc9b-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0dc9b-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="0dc9b-128">Namespace</span></span>|<span data-ttu-id="0dc9b-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0dc9b-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0dc9b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dc9b-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
