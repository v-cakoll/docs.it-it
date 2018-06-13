---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 1136647ce668dbb69bdb8acf8ed62343831464b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487776"
---
# <a name="wsattracerecord"></a><span data-ttu-id="cfaa8-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cfaa8-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="cfaa8-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cfaa8-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfaa8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfaa8-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cfaa8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="cfaa8-105">Methods</span></span>  
 <span data-ttu-id="cfaa8-106">La classe WSAT_TraceRecord non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="cfaa8-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cfaa8-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cfaa8-107">Properties</span></span>  
 <span data-ttu-id="cfaa8-108">La classe WSAT_TraceRecord dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfaa8-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="cfaa8-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="cfaa8-109">ActivityID</span></span>  
 <span data-ttu-id="cfaa8-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="cfaa8-110">Data type: object</span></span>  
<span data-ttu-id="cfaa8-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cfaa8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cfaa8-112">ID attività del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="cfaa8-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="cfaa8-113">ID evento</span><span class="sxs-lookup"><span data-stu-id="cfaa8-113">EventID</span></span>  
 <span data-ttu-id="cfaa8-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="cfaa8-114">Data type: sint32</span></span>  
<span data-ttu-id="cfaa8-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cfaa8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cfaa8-116">ID evento del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="cfaa8-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="cfaa8-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cfaa8-117">TraceRecord</span></span>  
 <span data-ttu-id="cfaa8-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="cfaa8-118">Data type: string</span></span>  
<span data-ttu-id="cfaa8-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cfaa8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cfaa8-120">Record di traccia</span><span class="sxs-lookup"><span data-stu-id="cfaa8-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfaa8-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cfaa8-121">Requirements</span></span>  
  
|<span data-ttu-id="cfaa8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="cfaa8-122">MOF</span></span>|<span data-ttu-id="cfaa8-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cfaa8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cfaa8-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="cfaa8-124">Namespace</span></span>|<span data-ttu-id="cfaa8-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cfaa8-125">Defined in root\ServiceModel</span></span>|
