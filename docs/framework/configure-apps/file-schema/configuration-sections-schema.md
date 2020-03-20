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
ms.openlocfilehash: 28f936e6fd7c9e7f6f895396df8e8b8d36ab9139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155323"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="29192-102">Schema delle sezioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="29192-102">Configuration sections schema</span></span>

<span data-ttu-id="29192-103">Lo schema delle sezioni di configurazione contiene elementi che definiscono le impostazioni personalizzate nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="29192-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="29192-104">Per informazioni generali sui file di configurazione e sugli schemi, vedere Schema del file di configurazione [per .NET Framework.](index.md)</span><span class="sxs-lookup"><span data-stu-id="29192-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="29192-105">[**\<configuration>** ](configuration-element.md) 
 
 [\*\* \< \*\*](clear-element-for-configsections.md) 
 [\*\* \< \*\*](remove-element-for-configsections.md) 
 [\*\* \< \*\*](section-element.md) 
 [\*\* \<\*\*](sectiongroup-element-for-configsections.md) configSezioni>>rimuovere>sezione>sezione>[\*\* \< \*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="29192-105">[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<clear>**](clear-element-for-configsections.md)
[**\<remove>**](remove-element-for-configsections.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>

|     | <span data-ttu-id="29192-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29192-106">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="29192-107">\*\* \<>\*\* per \*\* \<la>configSections\*\*</span><span class="sxs-lookup"><span data-stu-id="29192-107">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="29192-108">Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="29192-108">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="29192-109">**\<>chiari**</span><span class="sxs-lookup"><span data-stu-id="29192-109">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="29192-110">Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="29192-110">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="29192-111">**\<>configSections**</span><span class="sxs-lookup"><span data-stu-id="29192-111">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="29192-112">Contiene le dichiarazioni della sezione di configurazione e dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="29192-112">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="29192-113">rimuovere>per \*\* \<\*\* \*\* \<la>configSections\*\*</span><span class="sxs-lookup"><span data-stu-id="29192-113">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="29192-114">Rimuove una sezione o un gruppo di sezioni predefinito.</span><span class="sxs-lookup"><span data-stu-id="29192-114">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="29192-115">Sezione>per \*\* \<la>configSections\*\* e \*\* \<la>sectionGroup\*\* \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="29192-115">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="29192-116">Contiene una dichiarazione di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="29192-116">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="29192-117">>sectionGroup per \*\* \<\*\* \*\* \<configSections>\*\*</span><span class="sxs-lookup"><span data-stu-id="29192-117">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="29192-118">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="29192-118">Defines a namespace for configuration sections.</span></span> |
