---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 92aca4c790607de91314aacf6414d0dfacea9a9f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193162"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="1a6c1-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1a6c1-102">PeerSecuritySettings</span></span>
<span data-ttu-id="1a6c1-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1a6c1-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a6c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a6c1-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1a6c1-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1a6c1-105">Methods</span></span>  
 <span data-ttu-id="1a6c1-106">La classe PeerSecuritySettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="1a6c1-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1a6c1-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1a6c1-107">Properties</span></span>  
 <span data-ttu-id="1a6c1-108">La classe PeerSecuritySettings ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a6c1-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="1a6c1-109">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a6c1-109">Mode</span></span>  
 <span data-ttu-id="1a6c1-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="1a6c1-110">Data type: string</span></span>  
  
 <span data-ttu-id="1a6c1-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="1a6c1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1a6c1-112">Se un endpoint configurato con l'associazione utilizza meccanismi di sicurezza a livello di messaggio o di trasporto.</span><span class="sxs-lookup"><span data-stu-id="1a6c1-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="1a6c1-113">Trasporto</span><span class="sxs-lookup"><span data-stu-id="1a6c1-113">Transport</span></span>  
 <span data-ttu-id="1a6c1-114">Tipo di dati: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1a6c1-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="1a6c1-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="1a6c1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1a6c1-116">Impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="1a6c1-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a6c1-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a6c1-117">Requirements</span></span>  
  
|<span data-ttu-id="1a6c1-118">MOF</span><span class="sxs-lookup"><span data-stu-id="1a6c1-118">MOF</span></span>|<span data-ttu-id="1a6c1-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1a6c1-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1a6c1-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="1a6c1-120">Namespace</span></span>|<span data-ttu-id="1a6c1-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1a6c1-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a6c1-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a6c1-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
