---
title: Serializzazione-.NET
description: Questo articolo fornisce informazioni sulle tecnologie di serializzazione .NET, tra cui la serializzazione binaria, la serializzazione di XML e SOAP e la serializzazione JSON.
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: b3d76c14dc9180a5f19781122d1a42bcae603e76
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377247"
---
# <a name="serialization-in-net"></a><span data-ttu-id="92477-103">Serializzazione in .NET</span><span class="sxs-lookup"><span data-stu-id="92477-103">Serialization in .NET</span></span>

<span data-ttu-id="92477-104">La serializzazione è il processo di conversione dello stato di un oggetto in un form che può essere mantenuto o trasportato.</span><span class="sxs-lookup"><span data-stu-id="92477-104">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="92477-105">Il complemento della serializzazione è la deserializzazione, che converte un flusso in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="92477-105">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="92477-106">Insieme, questi processi consentono di archiviare e trasferire i dati.</span><span class="sxs-lookup"><span data-stu-id="92477-106">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="92477-107">.NET offre le seguenti tecnologie di serializzazione:</span><span class="sxs-lookup"><span data-stu-id="92477-107">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="92477-108">La [serializzazione binaria](binary-serialization.md) consente di mantenere la fedeltà dei tipi, utile per mantenere lo stato di un oggetto tra chiamate diverse di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92477-108">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="92477-109">È possibile, ad esempio, condividere un oggetto tra diverse applicazioni serializzandolo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="92477-109">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="92477-110">La serializzazione di un oggetto può essere effettuata in un flusso, in un disco, in memoria, in rete e così via.</span><span class="sxs-lookup"><span data-stu-id="92477-110">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="92477-111">.NET Remoting utilizza la serializzazione per passare oggetti "per valore" da un computer o dominio dell'applicazione a un altro.</span><span class="sxs-lookup"><span data-stu-id="92477-111">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="92477-112">La [serializzazione SOAP e XML](xml-and-soap-serialization.md) serializza solo i campi e le proprietà pubbliche e non mantiene la fedeltà del tipo.</span><span class="sxs-lookup"><span data-stu-id="92477-112">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="92477-113">Ciò risulta utile se si vuole fornire o utilizzare dati senza limitare l'applicazione che utilizza i dati.</span><span class="sxs-lookup"><span data-stu-id="92477-113">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="92477-114">Poiché XML è uno standard aperto, questa rappresenta una scelta interessante ai fini della condivisione di dati attraverso il Web.</span><span class="sxs-lookup"><span data-stu-id="92477-114">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="92477-115">Analogamente, SOAP è uno standard aperto che rappresenta una scelta altrettanto interessante.</span><span class="sxs-lookup"><span data-stu-id="92477-115">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="92477-116">La [serializzazione JSON](system-text-json-overview.md) serializza solo le proprietà pubbliche e non mantiene la fedeltà del tipo.</span><span class="sxs-lookup"><span data-stu-id="92477-116">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="92477-117">JSON è uno standard aperto che rappresenta una scelta interessante per la condivisione di dati sul Web.</span><span class="sxs-lookup"><span data-stu-id="92477-117">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="92477-118">Riferimento</span><span class="sxs-lookup"><span data-stu-id="92477-118">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="92477-119">Contiene classi utilizzabili per la serializzazione e la deserializzazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="92477-119">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="92477-120">Contiene classi utilizzabili per la serializzazione di oggetti in documenti XML o in flussi.</span><span class="sxs-lookup"><span data-stu-id="92477-120">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="92477-121">Contiene classi che possono essere usate per serializzare oggetti in flussi o documenti in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="92477-121">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>
