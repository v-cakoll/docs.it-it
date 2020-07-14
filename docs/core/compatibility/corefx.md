---
title: Modifiche di rilievo della libreria di classi base
description: Elenca le modifiche di rilievo nelle librerie .NET di base.
ms.date: 09/20/2019
ms.openlocfilehash: 64510809a1cf69ea0e4c4816eb2df54233e8eceb
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281304"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="63ee9-103">Modifiche di rilievo nelle librerie .NET Core</span><span class="sxs-lookup"><span data-stu-id="63ee9-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="63ee9-104">Le librerie .NET di base forniscono le primitive e altri tipi generali usati da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="63ee9-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="63ee9-105">In questa pagina sono documentate le modifiche di rilievo seguenti:</span><span class="sxs-lookup"><span data-stu-id="63ee9-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="63ee9-106">Modifica</span><span class="sxs-lookup"><span data-stu-id="63ee9-106">Breaking change</span></span> | <span data-ttu-id="63ee9-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="63ee9-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="63ee9-108">Il valore predefinito di ActivityIdFormat è W3C</span><span class="sxs-lookup"><span data-stu-id="63ee9-108">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="63ee9-109">5.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-109">5.0</span></span> |
| [<span data-ttu-id="63ee9-110">Modifica del comportamento per Vector2. Lerp e Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="63ee9-110">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="63ee9-111">5.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-111">5.0</span></span> |
| [<span data-ttu-id="63ee9-112">I metodi CompareGreaterThan SSE e SSE2 gestiscono correttamente gli input NaN</span><span class="sxs-lookup"><span data-stu-id="63ee9-112">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="63ee9-113">5.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-113">5.0</span></span> |
| [<span data-ttu-id="63ee9-114">Il contatore. CreateCounterSetInstance genera ora InvalidOperationException se l'istanza esiste già</span><span class="sxs-lookup"><span data-stu-id="63ee9-114">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="63ee9-115">5.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-115">5.0</span></span> |
| [<span data-ttu-id="63ee9-116">Pacchetto Microsoft. DotNet. PlatformAbstractions rimosso</span><span class="sxs-lookup"><span data-stu-id="63ee9-116">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="63ee9-117">5.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-117">5.0</span></span> |
| [<span data-ttu-id="63ee9-118">API che segnalano ora la versione del prodotto e non la versione del file</span><span class="sxs-lookup"><span data-stu-id="63ee9-118">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="63ee9-119">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-119">3.0</span></span> |
| [<span data-ttu-id="63ee9-120">Le istanze EncoderFallbackBuffer personalizzate non possono eseguire il fallback in modo ricorsivo</span><span class="sxs-lookup"><span data-stu-id="63ee9-120">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="63ee9-121">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-121">3.0</span></span> |
| [<span data-ttu-id="63ee9-122">Modifiche al comportamento di analisi e formattazione a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="63ee9-122">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="63ee9-123">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-123">3.0</span></span> |
| [<span data-ttu-id="63ee9-124">Le operazioni di analisi a virgola mobile non hanno più esito negativo o generano OverflowException</span><span class="sxs-lookup"><span data-stu-id="63ee9-124">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="63ee9-125">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-125">3.0</span></span> |
| [<span data-ttu-id="63ee9-126">InvalidAsynchronousStateException spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="63ee9-126">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="63ee9-127">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-127">3.0</span></span> |
| [<span data-ttu-id="63ee9-128">La sostituzione di sequenze di byte UTF-8 in formato non corretto segue le linee guida Unicode</span><span class="sxs-lookup"><span data-stu-id="63ee9-128">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="63ee9-129">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-129">3.0</span></span> |
| [<span data-ttu-id="63ee9-130">TypeDescriptionProviderAttribute spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="63ee9-130">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="63ee9-131">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-131">3.0</span></span> |
| [<span data-ttu-id="63ee9-132">ZipArchiveEntry non gestisce più gli archivi con dimensioni di voce incoerenti</span><span class="sxs-lookup"><span data-stu-id="63ee9-132">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="63ee9-133">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-133">3.0</span></span> |
| [<span data-ttu-id="63ee9-134">Tipo di eccezione del serializzatore JSON modificato da Jsonexception a NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="63ee9-134">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="63ee9-135">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-135">3.0</span></span> |
| [<span data-ttu-id="63ee9-136">Modifica della semantica di (String) null in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="63ee9-136">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="63ee9-137">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-137">3.0</span></span> |
| [<span data-ttu-id="63ee9-138">I metodi JsonEncodedText. Encode hanno un argomento JavaScriptEncoder aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="63ee9-138">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="63ee9-139">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-139">3.0</span></span> |
| [<span data-ttu-id="63ee9-140">Firma di JsonFactoryConverter. CreateConverter modificata</span><span class="sxs-lookup"><span data-stu-id="63ee9-140">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="63ee9-141">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-141">3.0</span></span> |
| [<span data-ttu-id="63ee9-142">Modifiche all'API jsonelement</span><span class="sxs-lookup"><span data-stu-id="63ee9-142">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="63ee9-143">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-143">3.0</span></span> |
| [<span data-ttu-id="63ee9-144">FieldInfo. SetValue genera un'eccezione per i campi statici di sola inizializzazione</span><span class="sxs-lookup"><span data-stu-id="63ee9-144">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="63ee9-145">3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-145">3.0</span></span> |
| [<span data-ttu-id="63ee9-146">Campi privati aggiunti ai tipi struct predefiniti</span><span class="sxs-lookup"><span data-stu-id="63ee9-146">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="63ee9-147">2.1</span><span class="sxs-lookup"><span data-stu-id="63ee9-147">2.1</span></span> |
| [<span data-ttu-id="63ee9-148">Modificare il valore predefinito di UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="63ee9-148">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="63ee9-149">2.1</span><span class="sxs-lookup"><span data-stu-id="63ee9-149">2.1</span></span> |
| [<span data-ttu-id="63ee9-150">Versioni OpenSSL in macOS</span><span class="sxs-lookup"><span data-stu-id="63ee9-150">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="63ee9-151">2.1</span><span class="sxs-lookup"><span data-stu-id="63ee9-151">2.1</span></span> |
| [<span data-ttu-id="63ee9-152">UnauthorizedAccessException generata da FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="63ee9-152">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="63ee9-153">1.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-153">1.0</span></span> |
| [<span data-ttu-id="63ee9-154">Gestione delle eccezioni di stato del processo danneggiato non supportata</span><span class="sxs-lookup"><span data-stu-id="63ee9-154">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="63ee9-155">1.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-155">1.0</span></span> |
| [<span data-ttu-id="63ee9-156">Le Proprietà UriBuilder non precedono più caratteri iniziali</span><span class="sxs-lookup"><span data-stu-id="63ee9-156">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="63ee9-157">1.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-157">1.0</span></span> |
| [<span data-ttu-id="63ee9-158">Process. StartInfo genera l'eccezione InvalidOperationException per i processi non avviati</span><span class="sxs-lookup"><span data-stu-id="63ee9-158">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="63ee9-159">1.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-159">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="63ee9-160">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="63ee9-160">.NET 5.0</span></span>

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

***

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

***

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="63ee9-161">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-161">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="63ee9-162">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="63ee9-162">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="63ee9-163">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="63ee9-163">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
