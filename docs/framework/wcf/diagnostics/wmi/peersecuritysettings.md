---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
ms.openlocfilehash: 18caaf2750fa3a263c09176e975204258330752c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371628"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="55425-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="55425-102">PeerSecuritySettings</span></span>
<span data-ttu-id="55425-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="55425-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55425-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55425-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="55425-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="55425-105">Methods</span></span>  
 <span data-ttu-id="55425-106">La classe PeerSecuritySettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="55425-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="55425-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="55425-107">Properties</span></span>  
 <span data-ttu-id="55425-108">La classe PeerSecuritySettings ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="55425-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="55425-109">Modalità</span><span class="sxs-lookup"><span data-stu-id="55425-109">Mode</span></span>  
 <span data-ttu-id="55425-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="55425-110">Data type: string</span></span>  
  
 <span data-ttu-id="55425-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="55425-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55425-112">Se un endpoint configurato con l'associazione utilizza meccanismi di sicurezza a livello di messaggio o di trasporto.</span><span class="sxs-lookup"><span data-stu-id="55425-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="55425-113">Trasporto</span><span class="sxs-lookup"><span data-stu-id="55425-113">Transport</span></span>  
 <span data-ttu-id="55425-114">Tipo di dati: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="55425-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="55425-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="55425-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55425-116">Impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="55425-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55425-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55425-117">Requirements</span></span>  
  
|<span data-ttu-id="55425-118">MOF</span><span class="sxs-lookup"><span data-stu-id="55425-118">MOF</span></span>|<span data-ttu-id="55425-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="55425-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="55425-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="55425-120">Namespace</span></span>|<span data-ttu-id="55425-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="55425-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55425-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55425-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
