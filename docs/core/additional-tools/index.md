---
title: Strumenti aggiuntivi per .NET Core
description: "Panoramica degli strumenti aggiuntivi che supportano ed estendono la funzionalità di .NET Core."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: article
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: 21fcc1190ee4586a8d7eb6fb8d63a7c312e63825
ms.sourcegitcommit: c1904b0437605a90e5aa65b4abd7e048000e349d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2018
---
# <a name="net-core-additional-tools"></a><span data-ttu-id="240be-103">Strumenti aggiuntivi per .NET Core</span><span class="sxs-lookup"><span data-stu-id="240be-103">.NET Core additional tools</span></span>

<span data-ttu-id="240be-104">Questa sezione consente di compilare un elenco di strumenti che supportano ed estendono la funzionalità di .NET Core, oltre agli strumenti [di interfaccia della riga di comando di .NET Core (CLI)](..\tools\index.md).</span><span class="sxs-lookup"><span data-stu-id="240be-104">This section compiles a list of tools that support and extend the .NET Core functionality, in addition to the [.NET Core command-line interface (CLI)](..\tools\index.md) tools.</span></span>

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[<span data-ttu-id="240be-105">Strumento di riferimento al servizio Web WCF</span><span class="sxs-lookup"><span data-stu-id="240be-105">WCF Web Service Reference Tool</span></span>](wcf-web-service-reference-guide.md)

<span data-ttu-id="240be-106">Il riferimento al servizio Web di WCF è un provider di servizi connessi di Visual Studio lanciato con la [versione 15.5 di Visual Studio 2017](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools).</span><span class="sxs-lookup"><span data-stu-id="240be-106">The WCF Web Service Reference is a Visual Studio connected service provider that made its debut in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools).</span></span> <span data-ttu-id="240be-107">Questo strumento consente di recuperare metadati da un servizio web nella soluzione corrente, in un percorso di rete o da un file WSDL e genera un file di origine compatibile con .NET Core contenente codice del proxy client Windows Communication Foundation (WCF) che è possibile usare per accedere al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="240be-107">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[<span data-ttu-id="240be-108">Generazione serializzatore XML</span><span class="sxs-lookup"><span data-stu-id="240be-108">XML Serializer Generator</span></span>](xml-serializer-generator.md)

<span data-ttu-id="240be-109">Come il [Generatore di serializzatori Xml (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) per .NET Framework, il [pacchetto Microsoft.XmlSerializer.Generator NuGet](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione per le librerie .NET Core e .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="240be-109">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the solution for .NET Core and .NET Standard libraries.</span></span> <span data-ttu-id="240be-110">Viene creato un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="240be-110">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>