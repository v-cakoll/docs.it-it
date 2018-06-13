---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 3548a1f19672a98ad0fc81eec15d5be29e5170bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486286"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="3e77b-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3e77b-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="3e77b-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3e77b-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e77b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e77b-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3e77b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3e77b-105">Methods</span></span>  
 <span data-ttu-id="3e77b-106">La classe NamedPipeConnectionPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="3e77b-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3e77b-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3e77b-107">Properties</span></span>  
 <span data-ttu-id="3e77b-108">La classe NamedPipeConnectionPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e77b-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="3e77b-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="3e77b-109">GroupName</span></span>  
 <span data-ttu-id="3e77b-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3e77b-110">Data type: string</span></span>  
  
 <span data-ttu-id="3e77b-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e77b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e77b-112">Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="3e77b-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="3e77b-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="3e77b-113">IdleTimeout</span></span>  
 <span data-ttu-id="3e77b-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="3e77b-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="3e77b-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e77b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e77b-116">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="3e77b-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="3e77b-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="3e77b-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="3e77b-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3e77b-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="3e77b-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e77b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e77b-120">Numero massimo di connessioni in uscita per ogni endpoint sul client.</span><span class="sxs-lookup"><span data-stu-id="3e77b-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e77b-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e77b-121">Requirements</span></span>  
  
|<span data-ttu-id="3e77b-122">MOF</span><span class="sxs-lookup"><span data-stu-id="3e77b-122">MOF</span></span>|<span data-ttu-id="3e77b-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3e77b-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3e77b-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3e77b-124">Namespace</span></span>|<span data-ttu-id="3e77b-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3e77b-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e77b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e77b-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
