---
title: 'Procedura: creare un''istanza di un oggetto TimeZoneInfo'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: defc8c9981b8476660c9c99d20bc50142ee9dfad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="64262-102">Procedura: creare un'istanza di un oggetto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="64262-102">How to: Instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="64262-103">Il modo più comune per creare un'istanza di un oggetto <xref:System.TimeZoneInfo> è recuperare le relative informazioni dal Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="64262-103">The most common way to instantiate a <xref:System.TimeZoneInfo> object is to retrieve information about it from the registry.</span></span> <span data-ttu-id="64262-104">In questo argomento viene illustrato come creare un'istanza di un oggetto <xref:System.TimeZoneInfo> dal Registro di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="64262-104">This topic discusses how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

### <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="64262-105">Per creare un'istanza di un oggetto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="64262-105">To instantiate a TimeZoneInfo object</span></span>

1. <span data-ttu-id="64262-106">Dichiarare un oggetto <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="64262-106">Declare a <xref:System.TimeZoneInfo> object.</span></span>

2. <span data-ttu-id="64262-107">Chiamare il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="64262-107">Call the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method.</span></span>

3. <span data-ttu-id="64262-108">Gestire tutte le eccezioni generate dal metodo, in particolare <xref:System.TimeZoneNotFoundException> , generata se il fuso orario non è definito nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="64262-108">Handle any exceptions thrown by the method, particularly the <xref:System.TimeZoneNotFoundException> that is thrown if the time zone is not defined in the registry.</span></span>

## <a name="example"></a><span data-ttu-id="64262-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="64262-109">Example</span></span>

<span data-ttu-id="64262-110">Nel codice seguente viene recuperato un oggetto <xref:System.TimeZoneInfo> che rappresenta il fuso Ora solare fuso orientale e viene visualizzata l'Ora solare fuso orientale che corrisponde all'ora locale.</span><span class="sxs-lookup"><span data-stu-id="64262-110">The following code retrieves a <xref:System.TimeZoneInfo> object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

<span data-ttu-id="64262-111">Il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> unico parametro del metodo è l'identificatore del fuso orario che si desidera recuperare, che corrisponde all'oggetto <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="64262-111">The <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="64262-112">L'identificatore del fuso orario è un campo chiave che identifica in modo univoco il fuso orario.</span><span class="sxs-lookup"><span data-stu-id="64262-112">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="64262-113">Benché la maggior parte delle chiavi sia relativamente breve, in confronto l'identificatore del fuso orario è piuttosto lungo.</span><span class="sxs-lookup"><span data-stu-id="64262-113">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="64262-114">In molti casi, il valore corrisponde alla proprietà <xref:System.TimeZoneInfo.StandardName%2A> di un oggetto <xref:System.TimeZoneInfo> , usato per fornire il nome dell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="64262-114">In most cases, its value corresponds to the <xref:System.TimeZoneInfo.StandardName%2A> property of a <xref:System.TimeZoneInfo> object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="64262-115">Esistono tuttavia alcune eccezioni.</span><span class="sxs-lookup"><span data-stu-id="64262-115">However, there are exceptions.</span></span> <span data-ttu-id="64262-116">Il modo migliore per verificare che venga fornito un identificatore valido consiste nell'enumerare i fusi orari disponibili nel sistema e annotare i relativi identificatori dei fusi orari.</span><span class="sxs-lookup"><span data-stu-id="64262-116">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="64262-117">Per informazioni generali, vedere [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="64262-117">For an illustration, see [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md).</span></span> <span data-ttu-id="64262-118">Nell'argomento [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) è presente inoltre un elenco di identificatori dei fusi orari selezionati.</span><span class="sxs-lookup"><span data-stu-id="64262-118">The [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="64262-119">Se il fuso orario viene trovato, il metodo restituisce l'oggetto <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="64262-119">If the time zone is found, the method returns its <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="64262-120">Se il fuso orario non viene trovato, il metodo genera un'eccezione <xref:System.TimeZoneNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="64262-120">If the time zone is not found, the method throws a <xref:System.TimeZoneNotFoundException>.</span></span> <span data-ttu-id="64262-121">Se invece il fuso orario viene trovato ma i dati sono danneggiati o incompleti, il metodo genera un'eccezione <xref:System.InvalidTimeZoneException>.</span><span class="sxs-lookup"><span data-stu-id="64262-121">If the time zone is found but its data is corrupted or incomplete, the method throws an <xref:System.InvalidTimeZoneException>.</span></span>

<span data-ttu-id="64262-122">Se l'applicazione si basa su un fuso orario che deve essere presente, chiamare prima il metodo <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> per recuperare le informazioni del fuso orario dal Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="64262-122">If your application relies on a time zone that must be present, you should first call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method to retrieve the time zone information from the registry.</span></span> <span data-ttu-id="64262-123">Se la chiamata al metodo non riesce, il gestore di eccezioni deve creare una nuova istanza del fuso orario o deve ricrearlo deserializzando un oggetto <xref:System.TimeZoneInfo> serializzato.</span><span class="sxs-lookup"><span data-stu-id="64262-123">If the method call fails, your exception handler should then either create a new instance of the time zone or re-create it by deserializing a serialized <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="64262-124">Vedere [procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) per un esempio.</span><span class="sxs-lookup"><span data-stu-id="64262-124">See [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) for an example.</span></span>

## <a name="see-also"></a><span data-ttu-id="64262-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64262-125">See also</span></span>

<span data-ttu-id="64262-126">[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[procedura: accedere a oggetti fuso UTC e l'ora locali predefiniti](../../../docs/standard/datetime/access-utc-and-local.md)</span><span class="sxs-lookup"><span data-stu-id="64262-126">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md)</span></span>
