---
title: Schema delle sezioni di configurazione
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: fc43a9c32ba33629b6e89120cf57f6d212ab3a56
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441661"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="bf1fc-102">Schema delle sezioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="bf1fc-102">Configuration sections schema</span></span>

<span data-ttu-id="bf1fc-103">Lo schema delle sezioni di configurazione contiene elementi che definiscono impostazioni personalizzate nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bf1fc-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="bf1fc-104">Per informazioni generali sui file di configurazione e sugli schemi, vedere [schema dei file di configurazione per il .NET Framework](index.md).</span><span class="sxs-lookup"><span data-stu-id="bf1fc-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="bf1fc-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf1fc-105">Description</span></span> |
| --- | ----------- |
| [**\<configSections>**](configsections-element-for-configuration.md) | <span data-ttu-id="bf1fc-106">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bf1fc-106">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="bf1fc-107">**\<section>** per **\<configSections>** e**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="bf1fc-107">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="bf1fc-108">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bf1fc-108">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="bf1fc-109">**\<sectionGroup>** per**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="bf1fc-109">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="bf1fc-110">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bf1fc-110">Defines a namespace for configuration sections.</span></span> |

<a name="dep"></a>

## <a name="unimplemented-elements"></a><span data-ttu-id="bf1fc-111">Elementi non implementati</span><span class="sxs-lookup"><span data-stu-id="bf1fc-111">Unimplemented elements</span></span>

<span data-ttu-id="bf1fc-112">Gli elementi seguenti non hanno alcun effetto e non devono essere usati:</span><span class="sxs-lookup"><span data-stu-id="bf1fc-112">The following elements have no impact and should not be used:</span></span>

* **\<clear>**
* **\<remove>**
