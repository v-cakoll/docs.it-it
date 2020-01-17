---
title: Modifiche di rilievo della libreria di classi base-.NET Core
description: Elenca le modifiche di rilievo apportate in .NET CoreFx, la libreria di classi di base.
ms.date: 09/20/2019
ms.openlocfilehash: eb416a0b061bfe50db330627c0ea68e0ba0c9079
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116511"
---
# <a name="corefx-breaking-changes"></a>CoreFx modifiche di rilievo

CoreFx fornisce le primitive e altri tipi generali usati da .NET Core.

In questa pagina sono documentate le modifiche di rilievo seguenti:

- [API che segnalano ora la versione del prodotto e non la versione del file](#apis-that-report-version-now-report-product-and-not-file-version)
- [Le istanze EncoderFallbackBuffer personalizzate non possono eseguire il fallback in modo ricorsivo](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively)
- [Modifiche al comportamento di analisi e formattazione a virgola mobile](#floating-point-formatting-and-parsing-behavior-changed)
- [Le operazioni di analisi a virgola mobile non hanno più esito negativo o generano OverflowException](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception)
- [InvalidAsynchronousStateException spostato in un altro assembly](#invalidasynchronousstateexception-moved-to-another-assembly)
- [NET Core 3,0 segue le procedure consigliate Unicode per la sostituzione di sequenze di byte UTF-8 in formato non valido](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences)
- [TypeDescriptionProviderAttribute spostato in un altro assembly](#typedescriptionproviderattribute-moved-to-another-assembly)
- [ZipArchiveEntry non gestisce più gli archivi con dimensioni di voce incoerenti](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes)
- [Tipo di eccezione del serializzatore JSON modificato da Jsonexception a NotSupportedException](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception)
- [Modifica della semantica di (String) null in Utf8JsonWriter](#change-in-semantics-of-stringnull-in-utf8jsonwriter)
- [I metodi JsonEncodedText. Encode hanno un argomento JavaScriptEncoder aggiuntivo](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument)
- [Firma di JsonFactoryConverter. CreateConverter modificata](#jsonfactoryconvertercreateconverter-signature-changed)
- [Modifiche all'API jsonelement](#jsonelement-api-changes)
- [Campi privati aggiunti ai tipi struct predefiniti](#private-fields-added-to-built-in-struct-types)
- [Modificare il valore predefinito di UseShellExecute](#change-in-default-value-of-useshellexecute)

## <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="net-core-30-preview-9"></a>.NET Core 3,0 Preview 9

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

## <a name="net-core-30-preview-8"></a>.NET Core 3,0 Preview 8

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

## <a name="net-core-30-preview-7"></a>.NET Core 3,0 Preview 7

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***
