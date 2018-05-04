---
title: Strumenti aggiuntivi per .NET Core
description: Panoramica degli strumenti aggiuntivi che supportano ed estendono la funzionalità di .NET Core.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: 578d42e5a0a11ae76410289142d47c8d65abe7aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="net-core-additional-tools"></a>Strumenti aggiuntivi per .NET Core

Questa sezione consente di compilare un elenco di strumenti che supportano ed estendono la funzionalità di .NET Core, oltre agli strumenti [di interfaccia della riga di comando di .NET Core (CLI)](..\tools\index.md).

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[Strumento di riferimento al servizio Web WCF](wcf-web-service-reference-guide.md)

Il riferimento al servizio Web di WCF è un provider di servizi connessi di Visual Studio lanciato con la [versione 15.5 di Visual Studio 2017](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools). Questo strumento consente di recuperare metadati da un servizio web nella soluzione corrente, in un percorso di rete o da un file WSDL e genera un file di origine compatibile con .NET Core contenente codice del proxy client Windows Communication Foundation (WCF) che è possibile usare per accedere al servizio Web.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[Generazione serializzatore XML](xml-serializer-generator.md)

Come il [Generatore di serializzatori Xml (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) per .NET Framework, il [pacchetto Microsoft.XmlSerializer.Generator NuGet](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione per le librerie .NET Core e .NET Standard. Viene creato un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.