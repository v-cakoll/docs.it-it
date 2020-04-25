---
title: Modifiche di rilievo della libreria di classi base
description: Elenca le modifiche di rilievo nelle librerie .NET di base.
ms.date: 09/20/2019
ms.openlocfilehash: bc80f27a8a98890a93ad3b99e09ea7ea380d506c
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158477"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="4a3bc-103">Modifiche di rilievo nelle librerie .NET Core</span><span class="sxs-lookup"><span data-stu-id="4a3bc-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="4a3bc-104">Le librerie .NET di base forniscono le primitive e altri tipi generali usati da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="4a3bc-105">In questa pagina sono documentate le modifiche di rilievo seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a3bc-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="4a3bc-106">Modifica</span><span class="sxs-lookup"><span data-stu-id="4a3bc-106">Breaking change</span></span> | <span data-ttu-id="4a3bc-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4a3bc-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="4a3bc-108">API che segnalano ora la versione del prodotto e non la versione del file</span><span class="sxs-lookup"><span data-stu-id="4a3bc-108">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="4a3bc-109">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-109">3.0</span></span> |
| [<span data-ttu-id="4a3bc-110">Le istanze EncoderFallbackBuffer personalizzate non possono eseguire il fallback in modo ricorsivo</span><span class="sxs-lookup"><span data-stu-id="4a3bc-110">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="4a3bc-111">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-111">3.0</span></span> |
| [<span data-ttu-id="4a3bc-112">Modifiche al comportamento di analisi e formattazione a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="4a3bc-112">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="4a3bc-113">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-113">3.0</span></span> |
| [<span data-ttu-id="4a3bc-114">Le operazioni di analisi a virgola mobile non hanno più esito negativo o generano OverflowException</span><span class="sxs-lookup"><span data-stu-id="4a3bc-114">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="4a3bc-115">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-115">3.0</span></span> |
| [<span data-ttu-id="4a3bc-116">InvalidAsynchronousStateException spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="4a3bc-116">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="4a3bc-117">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-117">3.0</span></span> |
| [<span data-ttu-id="4a3bc-118">La sostituzione di sequenze di byte UTF-8 in formato non corretto segue le linee guida Unicode</span><span class="sxs-lookup"><span data-stu-id="4a3bc-118">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="4a3bc-119">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-119">3.0</span></span> |
| [<span data-ttu-id="4a3bc-120">TypeDescriptionProviderAttribute spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="4a3bc-120">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="4a3bc-121">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-121">3.0</span></span> |
| [<span data-ttu-id="4a3bc-122">ZipArchiveEntry non gestisce più gli archivi con dimensioni di voce incoerenti</span><span class="sxs-lookup"><span data-stu-id="4a3bc-122">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="4a3bc-123">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-123">3.0</span></span> |
| [<span data-ttu-id="4a3bc-124">Tipo di eccezione del serializzatore JSON modificato da Jsonexception a NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="4a3bc-124">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="4a3bc-125">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-125">3.0</span></span> |
| [<span data-ttu-id="4a3bc-126">Modifica della semantica di (String) null in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="4a3bc-126">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="4a3bc-127">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-127">3.0</span></span> |
| [<span data-ttu-id="4a3bc-128">I metodi JsonEncodedText. Encode hanno un argomento JavaScriptEncoder aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="4a3bc-128">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="4a3bc-129">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-129">3.0</span></span> |
| [<span data-ttu-id="4a3bc-130">Firma di JsonFactoryConverter. CreateConverter modificata</span><span class="sxs-lookup"><span data-stu-id="4a3bc-130">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="4a3bc-131">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-131">3.0</span></span> |
| [<span data-ttu-id="4a3bc-132">Modifiche all'API jsonelement</span><span class="sxs-lookup"><span data-stu-id="4a3bc-132">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="4a3bc-133">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-133">3.0</span></span> |
| [<span data-ttu-id="4a3bc-134">FieldInfo. SetValue genera un'eccezione per i campi statici di sola inizializzazione</span><span class="sxs-lookup"><span data-stu-id="4a3bc-134">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="4a3bc-135">3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-135">3.0</span></span> |
| [<span data-ttu-id="4a3bc-136">Campi privati aggiunti ai tipi struct predefiniti</span><span class="sxs-lookup"><span data-stu-id="4a3bc-136">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="4a3bc-137">2.1</span><span class="sxs-lookup"><span data-stu-id="4a3bc-137">2.1</span></span> |
| [<span data-ttu-id="4a3bc-138">Modificare il valore predefinito di UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="4a3bc-138">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="4a3bc-139">2.1</span><span class="sxs-lookup"><span data-stu-id="4a3bc-139">2.1</span></span> |
| [<span data-ttu-id="4a3bc-140">Versioni OpenSSL in macOS</span><span class="sxs-lookup"><span data-stu-id="4a3bc-140">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="4a3bc-141">2.1</span><span class="sxs-lookup"><span data-stu-id="4a3bc-141">2.1</span></span> |
| [<span data-ttu-id="4a3bc-142">UnauthorizedAccessException generata da FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="4a3bc-142">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="4a3bc-143">1.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-143">1.0</span></span> |
| [<span data-ttu-id="4a3bc-144">Gestione delle eccezioni di stato del processo danneggiato non supportata</span><span class="sxs-lookup"><span data-stu-id="4a3bc-144">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="4a3bc-145">1.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-145">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="4a3bc-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-146">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

***

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="4a3bc-147">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4a3bc-147">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="4a3bc-148">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4a3bc-148">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***
