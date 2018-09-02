---
title: Strumenti aggiuntivi per .NET Core
description: Panoramica degli strumenti aggiuntivi che supportano ed estendono la funzionalità di .NET Core.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: ba63ef6cdc092d06e267637112070e7cd5133a45
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456383"
---
# <a name="net-core-additional-tools"></a>Strumenti aggiuntivi per .NET Core

Questa sezione consente di compilare un elenco di strumenti che supportano ed estendono la funzionalità di .NET Core, oltre agli strumenti [di interfaccia della riga di comando di .NET Core (CLI)](..\tools\index.md).

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[Strumento WCF Web Service Reference](wcf-web-service-reference-guide.md)

WCF (Windows Communication Foundation) Web Service Reference è un provider di servizi connessi di Visual Studio disponibile per la prima volta con [Visual Studio 2017 versione 15.5](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools). Questo strumento consente di recuperare metadati da un servizio Web nella soluzione corrente, in un percorso di rete o da un file WSDL, e genera un file di origine compatibile con .NET Core che definisce una classe proxy WCF con metodi utilizzabili per accedere alle operazioni del servizio Web.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[Strumento WCF dotnet-svcutil](dotnet-svcutil-guide.md)

Lo strumento WCF (Windows Communication Foundation) dotnet-svcutil consente di recuperare metadati da un servizio Web, in un percorso di rete o da un file WSDL e genera un file di origine compatibile con .NET Core che definisce una classe proxy WCF con metodi utilizzabili per accedere alle operazioni del servizio Web. Lo strumento **dotnet-svcutil** rappresenta un'alternativa al provider di servizi connessi di Visuali Studio [ **WCF Web Service Reference** ](wcf-web-service-reference-guide.md), disponibile per la prima volta con Visual Studio 2017 versione 15.5. Come strumento dell'interfaccia della riga di comando di .NET Core, **dotnet-svcutil** è disponibile come strumento multipiattaforma in Linux, macOS e Windows.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[Generazione serializzatore XML](xml-serializer-generator.md)

Come il [Generatore di serializzatori Xml (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) per .NET Framework, il [pacchetto Microsoft.XmlSerializer.Generator NuGet](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione per le librerie .NET Core e .NET Standard. Viene creato un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.