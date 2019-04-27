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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: edd2b2e11b02d69b7bba7c3cc7d8a9a0814e0c51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674818"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="7b4a7-102">Schema delle sezioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="7b4a7-102">Configuration sections schema</span></span>

<span data-ttu-id="7b4a7-103">Lo schema di sezioni di configurazione contiene elementi che definiscono le impostazioni personalizzate nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7b4a7-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="7b4a7-104">Per informazioni generali su schemi e i file di configurazione, vedere [schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="7b4a7-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="7b4a7-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7b4a7-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7b4a7-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7b4a7-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="7b4a7-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="7b4a7-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="7b4a7-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="7b4a7-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="7b4a7-109">[**\<sezione >**](~/docs/framework/configure-apps/file-schema/section-element.md) </span><span class="sxs-lookup"><span data-stu-id="7b4a7-109">[**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) </span></span>  
[<span data-ttu-id="7b4a7-110">**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="7b4a7-110">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="7b4a7-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b4a7-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7b4a7-112">**\<Cancella >** per  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="7b4a7-112">**\<clear>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="7b4a7-113">Cancella tutte le sezioni definite in precedenza e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="7b4a7-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="7b4a7-114">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="7b4a7-114">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="7b4a7-115">Cancella tutte le sezioni definite in precedenza e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="7b4a7-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="7b4a7-116">**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="7b4a7-116">**\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="7b4a7-117">Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7b4a7-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="7b4a7-118">**\<rimuovere >** per  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="7b4a7-118">**\<remove>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="7b4a7-119">Rimuove una sezione predefiniti o un gruppo di sezioni.</span><span class="sxs-lookup"><span data-stu-id="7b4a7-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="7b4a7-120">**\<sezione >** per  **\<configSections >** e  **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="7b4a7-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="7b4a7-121">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7b4a7-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="7b4a7-122">**\<sectionGroup >** per  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="7b4a7-122">**\<sectionGroup>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="7b4a7-123">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7b4a7-123">Defines a namespace for configuration sections.</span></span> |
