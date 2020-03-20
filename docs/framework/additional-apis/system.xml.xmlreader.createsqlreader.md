---
title: Metodo XmlReader.CreateSqlReader (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155739"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="b7b4d-102">Metodo XmlReader.CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="b7b4d-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="b7b4d-103">Crea una nuova istanza di <xref:System.Xml.XmlReader> con il flusso, le impostazioni e le informazioni di contesto specificati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="b7b4d-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7b4d-104">Parameters</span></span>

- <span data-ttu-id="b7b4d-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="b7b4d-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="b7b4d-106">Flusso che contiene i dati XML.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="b7b4d-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="b7b4d-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="b7b4d-108">Impostazioni per la nuova istanza di <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="b7b4d-109">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-109">This value can be `null`.</span></span>

- <span data-ttu-id="b7b4d-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="b7b4d-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="b7b4d-111">Informazioni sul contesto necessarie per analizzare il frammento XML.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="b7b4d-112">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="b7b4d-113">Valori di codice restituiti</span><span class="sxs-lookup"><span data-stu-id="b7b4d-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="b7b4d-114">Oggetto usato per leggere i dati XML nel flusso.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7b4d-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b7b4d-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="b7b4d-116">Il `XmlReader.CreateSqlReader` metodo è interno e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b7b4d-117">Microsoft non supporta in nessun caso l'utilizzo di questo metodo in un'applicazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7b4d-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7b4d-118">Requirements</span></span>

<span data-ttu-id="b7b4d-119">**Spazio dei nomi:**<xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="b7b4d-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="b7b4d-120">**Assemblaggio:** System.xml.dll</span><span class="sxs-lookup"><span data-stu-id="b7b4d-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="b7b4d-121">Versioni di **.NET Framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="b7b4d-121">**.NET Framework versions:** Available since 2.0.</span></span>
