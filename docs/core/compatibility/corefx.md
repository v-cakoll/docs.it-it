---
title: Modifiche di rilievo CoreFx-.NET Core
description: Elenca le modifiche di rilievo apportate in .NET CoreFx, la libreria di classi di base.
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3838bcd7c127860a8307fe31bd85ed5addffb59e
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71272706"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="1a947-103">CoreFx modifiche di rilievo</span><span class="sxs-lookup"><span data-stu-id="1a947-103">CoreFx breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a947-104">Questo articolo è in costruzione.</span><span class="sxs-lookup"><span data-stu-id="1a947-104">This article is under construction.</span></span> <span data-ttu-id="1a947-105">Questo non è un elenco completo delle modifiche di rilievo di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1a947-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="1a947-106">Per altre informazioni sulle modifiche di rilievo di .NET Core, è possibile esaminare i singoli [problemi di modifiche di rilievo](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) nel repository DotNet/docs su GitHub.</span><span class="sxs-lookup"><span data-stu-id="1a947-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span>

<span data-ttu-id="1a947-107">Di seguito è riportato un elenco di modifiche di rilievo CoreFx per la versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1a947-107">The following is a list of CoreFx breaking changes by .NET Core version.</span></span> <span data-ttu-id="1a947-108">CoreFx fornisce le primitive e altri tipi generali usati da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1a947-108">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

## <a name="net-core-30-preview-7"></a><span data-ttu-id="1a947-109">.NET Core 3,0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="1a947-109">.NET Core 3.0 Preview 7</span></span>

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/jsonelement-api-changes.md)]

## <a name="net-core-30-preview-8"></a><span data-ttu-id="1a947-110">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="1a947-110">.NET Core 3.0 Preview 8</span></span>

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/jsonfactoryconverter-createconverter.md)]

## <a name="net-core-30-preview-9"></a><span data-ttu-id="1a947-111">.NET Core 3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="1a947-111">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Json serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/serializer-throws-notsupportedexception.md)]

## <a name="net-core-30"></a><span data-ttu-id="1a947-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1a947-112">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/floating-point-changes.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/ziparchiveentry-and-inconsistent-entry-sizes.md)]
