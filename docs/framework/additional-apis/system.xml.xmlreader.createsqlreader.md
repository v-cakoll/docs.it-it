---
title: Metodo XmlReader. CreateSqlReader (System. Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: c65ef7c073175488c11c5e912a44d46fd4319209
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215454"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="880e4-102">Metodo XmlReader.CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="880e4-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="880e4-103">Crea una nuova istanza di <xref:System.Xml.XmlReader> con il flusso, le impostazioni e le informazioni di contesto specificati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="880e4-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="880e4-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="880e4-104">Parameters</span></span>

- <span data-ttu-id="880e4-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="880e4-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="880e4-106">Flusso che contiene i dati XML.</span><span class="sxs-lookup"><span data-stu-id="880e4-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="880e4-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="880e4-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="880e4-108">Impostazioni per la nuova istanza di <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="880e4-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="880e4-109">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="880e4-109">This value can be `null`.</span></span>

- <span data-ttu-id="880e4-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="880e4-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="880e4-111">Informazioni sul contesto necessarie per analizzare il frammento XML.</span><span class="sxs-lookup"><span data-stu-id="880e4-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="880e4-112">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="880e4-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="880e4-113">Valori di codice restituiti</span><span class="sxs-lookup"><span data-stu-id="880e4-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="880e4-114">Oggetto usato per leggere i dati XML nel flusso.</span><span class="sxs-lookup"><span data-stu-id="880e4-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="880e4-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="880e4-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="880e4-116">Il `XmlReader.CreateSqlReader` metodo è interno e non deve essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="880e4-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="880e4-117">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="880e4-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="880e4-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="880e4-118">Requirements</span></span>

<span data-ttu-id="880e4-119">**Spazio dei nomi:** <xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="880e4-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="880e4-120">**Assembly:** System. XML. dll</span><span class="sxs-lookup"><span data-stu-id="880e4-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="880e4-121">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="880e4-121">**.NET Framework versions:** Available since 2.0.</span></span>
