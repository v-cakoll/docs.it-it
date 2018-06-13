---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: ee7cfed20234175ba54dd25dbbbab4615c1ed7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485755"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="8c238-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="8c238-102">OneWayBindingElement</span></span>
<span data-ttu-id="8c238-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="8c238-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c238-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c238-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8c238-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="8c238-105">Methods</span></span>  
 <span data-ttu-id="8c238-106">La classe OneWayBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="8c238-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8c238-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8c238-107">Properties</span></span>  
 <span data-ttu-id="8c238-108">La classe OneWayBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c238-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="8c238-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8c238-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="8c238-110">Tipo di dati: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8c238-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="8c238-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="8c238-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8c238-112">Impostazioni del pool di canali.</span><span class="sxs-lookup"><span data-stu-id="8c238-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="8c238-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="8c238-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="8c238-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="8c238-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="8c238-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="8c238-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8c238-116">Numero massimo di canali accettati.</span><span class="sxs-lookup"><span data-stu-id="8c238-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="8c238-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="8c238-117">PacketRoutable</span></span>  
 <span data-ttu-id="8c238-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="8c238-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="8c238-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="8c238-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8c238-120">Valore che indica se il pacchetto è instradabile.</span><span class="sxs-lookup"><span data-stu-id="8c238-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c238-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c238-121">Requirements</span></span>  
  
|<span data-ttu-id="8c238-122">MOF</span><span class="sxs-lookup"><span data-stu-id="8c238-122">MOF</span></span>|<span data-ttu-id="8c238-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8c238-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8c238-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="8c238-124">Namespace</span></span>|<span data-ttu-id="8c238-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8c238-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c238-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c238-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
