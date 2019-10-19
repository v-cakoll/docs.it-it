---
title: Metodo XmlReader. CreateSqlReader (System. Xml)
author: mairaw
ms.author: mairaw
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 302be4eff32d2c96a1571d291e0b289e77694db8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72584134"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="4f31d-102">XmlReader. CreateSqlReader, metodo</span><span class="sxs-lookup"><span data-stu-id="4f31d-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="4f31d-103">Crea una nuova istanza di <xref:System.Xml.XmlReader> con il flusso, le impostazioni e le informazioni di contesto specificati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="4f31d-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="4f31d-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f31d-104">Parameters</span></span>

- <span data-ttu-id="4f31d-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="4f31d-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="4f31d-106">Flusso che contiene i dati XML.</span><span class="sxs-lookup"><span data-stu-id="4f31d-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="4f31d-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="4f31d-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="4f31d-108">Impostazioni per la nuova istanza di <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="4f31d-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="4f31d-109">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="4f31d-109">This value can be `null`.</span></span>

- <span data-ttu-id="4f31d-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="4f31d-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="4f31d-111">Informazioni sul contesto necessarie per analizzare il frammento XML.</span><span class="sxs-lookup"><span data-stu-id="4f31d-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="4f31d-112">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="4f31d-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="4f31d-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4f31d-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="4f31d-114">Oggetto usato per leggere i dati XML nel flusso.</span><span class="sxs-lookup"><span data-stu-id="4f31d-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f31d-115">Note</span><span class="sxs-lookup"><span data-stu-id="4f31d-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="4f31d-116">Il `XmlReader.CreateSqlReader` metodo è interno e non deve essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="4f31d-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4f31d-117">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="4f31d-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4f31d-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f31d-118">Requirements</span></span>

<span data-ttu-id="4f31d-119">**Spazio dei nomi:** <xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="4f31d-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="4f31d-120">**Assembly:** System. XML. dll</span><span class="sxs-lookup"><span data-stu-id="4f31d-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="4f31d-121">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="4f31d-121">**.NET Framework versions:** Available since 2.0.</span></span>
