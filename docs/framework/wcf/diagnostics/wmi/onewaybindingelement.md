---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 016ff823eb2c84a9f54c0763edadef1224e31517
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040048"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="440d4-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="440d4-102">OneWayBindingElement</span></span>
<span data-ttu-id="440d4-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="440d4-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="440d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="440d4-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="440d4-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="440d4-105">Methods</span></span>  
 <span data-ttu-id="440d4-106">La classe OneWayBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="440d4-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="440d4-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="440d4-107">Properties</span></span>  
 <span data-ttu-id="440d4-108">La classe OneWayBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="440d4-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="440d4-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="440d4-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="440d4-110">Tipo di dati: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="440d4-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="440d4-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="440d4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="440d4-112">Impostazioni del pool di canali.</span><span class="sxs-lookup"><span data-stu-id="440d4-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="440d4-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="440d4-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="440d4-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="440d4-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="440d4-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="440d4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="440d4-116">Numero massimo di canali accettati.</span><span class="sxs-lookup"><span data-stu-id="440d4-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="440d4-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="440d4-117">PacketRoutable</span></span>  
 <span data-ttu-id="440d4-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="440d4-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="440d4-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="440d4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="440d4-120">Valore che indica se il pacchetto è instradabile.</span><span class="sxs-lookup"><span data-stu-id="440d4-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="440d4-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="440d4-121">Requirements</span></span>  
  
|<span data-ttu-id="440d4-122">MOF</span><span class="sxs-lookup"><span data-stu-id="440d4-122">MOF</span></span>|<span data-ttu-id="440d4-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="440d4-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="440d4-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="440d4-124">Namespace</span></span>|<span data-ttu-id="440d4-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="440d4-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="440d4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="440d4-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
