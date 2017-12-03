---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abaacfb6541d41019a8d0cd6df53913c6b7911f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="aee69-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="aee69-102">OneWayBindingElement</span></span>
<span data-ttu-id="aee69-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="aee69-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aee69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aee69-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="aee69-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="aee69-105">Methods</span></span>  
 <span data-ttu-id="aee69-106">La classe OneWayBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="aee69-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="aee69-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="aee69-107">Properties</span></span>  
 <span data-ttu-id="aee69-108">La classe OneWayBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="aee69-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="aee69-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="aee69-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="aee69-110">Tipo di dati: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="aee69-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="aee69-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="aee69-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aee69-112">Impostazioni del pool di canali.</span><span class="sxs-lookup"><span data-stu-id="aee69-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="aee69-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="aee69-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="aee69-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="aee69-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="aee69-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="aee69-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aee69-116">Numero massimo di canali accettati.</span><span class="sxs-lookup"><span data-stu-id="aee69-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="aee69-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="aee69-117">PacketRoutable</span></span>  
 <span data-ttu-id="aee69-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="aee69-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="aee69-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="aee69-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aee69-120">Valore che indica se il pacchetto è instradabile.</span><span class="sxs-lookup"><span data-stu-id="aee69-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aee69-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aee69-121">Requirements</span></span>  
  
|<span data-ttu-id="aee69-122">MOF</span><span class="sxs-lookup"><span data-stu-id="aee69-122">MOF</span></span>|<span data-ttu-id="aee69-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="aee69-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="aee69-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="aee69-124">Namespace</span></span>|<span data-ttu-id="aee69-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aee69-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aee69-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aee69-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
