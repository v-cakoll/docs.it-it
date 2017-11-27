---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c130093b9600c324e7179febce6857341b8a7d3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="transportbindingelement"></a><span data-ttu-id="36116-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="36116-102">TransportBindingElement</span></span>
<span data-ttu-id="36116-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="36116-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36116-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36116-104">Syntax</span></span>  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="36116-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="36116-105">Methods</span></span>  
 <span data-ttu-id="36116-106">La classe TransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="36116-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="36116-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="36116-107">Properties</span></span>  
 <span data-ttu-id="36116-108">La classe TransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="36116-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="36116-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="36116-109">ManualAddressing</span></span>  
 <span data-ttu-id="36116-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="36116-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="36116-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="36116-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36116-112">Valore booleano che specifica se l'utente desidera controllare l'indirizzamento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="36116-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="36116-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="36116-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="36116-114">Tipo di dati: sint64</span><span class="sxs-lookup"><span data-stu-id="36116-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="36116-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="36116-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36116-116">Dimensioni massime del pool di buffer dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="36116-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="36116-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="36116-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="36116-118">Tipo di dati: sint64</span><span class="sxs-lookup"><span data-stu-id="36116-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="36116-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="36116-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36116-120">Dimensioni massime di un messaggio elaborato dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="36116-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="36116-121">Scheme</span><span class="sxs-lookup"><span data-stu-id="36116-121">Scheme</span></span>  
 <span data-ttu-id="36116-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="36116-122">Data type: string</span></span>  
  
 <span data-ttu-id="36116-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="36116-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36116-124">Schema URI del trasporto.</span><span class="sxs-lookup"><span data-stu-id="36116-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36116-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36116-125">Requirements</span></span>  
  
|<span data-ttu-id="36116-126">MOF</span><span class="sxs-lookup"><span data-stu-id="36116-126">MOF</span></span>|<span data-ttu-id="36116-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="36116-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="36116-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="36116-128">Namespace</span></span>|<span data-ttu-id="36116-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="36116-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36116-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36116-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
