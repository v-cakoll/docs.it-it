---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: aed65311d2b36a5dc764511de04e34c4bfb69d7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963246"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="4b8f2-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="4b8f2-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="4b8f2-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="4b8f2-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b8f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b8f2-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4b8f2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4b8f2-105">Methods</span></span>  
 <span data-ttu-id="4b8f2-106">La classe MtomMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4b8f2-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4b8f2-107">Properties</span></span>  
 <span data-ttu-id="4b8f2-108">La classe MtomMessageEncodingBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b8f2-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="4b8f2-109">Codifica</span><span class="sxs-lookup"><span data-stu-id="4b8f2-109">Encoding</span></span>  
 <span data-ttu-id="4b8f2-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4b8f2-110">Data type: string</span></span>  
  
 <span data-ttu-id="4b8f2-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b8f2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b8f2-112">Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="4b8f2-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4b8f2-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="4b8f2-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="4b8f2-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b8f2-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b8f2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b8f2-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="4b8f2-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4b8f2-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="4b8f2-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="4b8f2-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b8f2-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b8f2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b8f2-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="4b8f2-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4b8f2-121">ReaderQuotas</span></span>  
 <span data-ttu-id="4b8f2-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4b8f2-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="4b8f2-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b8f2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b8f2-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b8f2-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b8f2-125">Requirements</span></span>  
  
|<span data-ttu-id="4b8f2-126">MOF</span><span class="sxs-lookup"><span data-stu-id="4b8f2-126">MOF</span></span>|<span data-ttu-id="4b8f2-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4b8f2-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4b8f2-128">Namespace</span></span>|<span data-ttu-id="4b8f2-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4b8f2-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b8f2-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b8f2-130">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
