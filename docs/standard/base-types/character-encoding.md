---
title: Codifica dei caratteri in .NET
description: Codifica dei caratteri in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bce54e41-e9dc-493a-8988-1cbadc340fe8
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a8f42fa6a37f8de6f13186ea2ac17b2b2ced1601
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="character-encoding-in-net"></a><span data-ttu-id="299ef-104">Codifica dei caratteri in .NET</span><span class="sxs-lookup"><span data-stu-id="299ef-104">Character encoding in .NET</span></span>

<span data-ttu-id="299ef-105">I caratteri sono entità astratte rappresentabili in molti modi.</span><span class="sxs-lookup"><span data-stu-id="299ef-105">Characters are abstract entities that can be represented in many different ways.</span></span> <span data-ttu-id="299ef-106">La codifica dei caratteri è un sistema che abbina ogni carattere di un set di caratteri supportato a un valore che lo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="299ef-106">A character encoding is a system that pairs each character in a supported character set with some value that represents that character.</span></span> <span data-ttu-id="299ef-107">Il codice Morse, ad esempio, è una codifica dei caratteri che abbina ogni carattere dell'alfabeto romano a una serie di punti e linee utilizzabili per la trasmissione su linee telegrafiche.</span><span class="sxs-lookup"><span data-stu-id="299ef-107">For example, Morse code is a character encoding that pairs each character in the Roman alphabet with a pattern of dots and dashes that are suitable for transmission over telegraph lines.</span></span> <span data-ttu-id="299ef-108">La codifica dei caratteri per i computer abbina ogni carattere di un set di caratteri supportato a un valore numerico che lo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="299ef-108">A character encoding for computers pairs each character in a supported character set with a numeric value that represents that character.</span></span> <span data-ttu-id="299ef-109">La codifica dei caratteri presenta due componenti distinti:</span><span class="sxs-lookup"><span data-stu-id="299ef-109">A character encoding has two distinct components:</span></span>

* <span data-ttu-id="299ef-110">Un codificatore, che converte una sequenza di caratteri in una sequenza di valori numerici (byte).</span><span class="sxs-lookup"><span data-stu-id="299ef-110">An encoder, which translates a sequence of characters into a sequence of numeric values (bytes).</span></span>

* <span data-ttu-id="299ef-111">Un decodificatore, che converte una sequenza di byte in una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="299ef-111">A decoder, which translates a sequence of bytes into a sequence of characters.</span></span>

<span data-ttu-id="299ef-112">La codifica dei caratteri descrive le regole in base alle quali operano un codificatore e un decodificatore.</span><span class="sxs-lookup"><span data-stu-id="299ef-112">Character encoding describes the rules by which an encoder and a decoder operate.</span></span> <span data-ttu-id="299ef-113">Ad esempio, la classe [UTF8Encoding](xref:System.Text.UTF8Encoding) descrive le regole per la codifica e la decodifica con UTF-8 (Unicode Transformation Format a 8 bit), che usa da uno a quattro byte per rappresentare un singolo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="299ef-113">For example, the [UTF8Encoding](xref:System.Text.UTF8Encoding) class describes the rules for encoding to, and decoding from, 8-bit Unicode Transformation Format (UTF-8), which uses one to four bytes to represent a single Unicode character.</span></span> <span data-ttu-id="299ef-114">La codifica e la decodifica possono includere anche la convalida.</span><span class="sxs-lookup"><span data-stu-id="299ef-114">Encoding and decoding can also include validation.</span></span> <span data-ttu-id="299ef-115">Ad esempio, la classe [UnicodeEncoding](xref:System.Text.UnicodeEncoding) controlla tutti i surrogati per assicurarsi che costituiscano coppie di surrogati valide.</span><span class="sxs-lookup"><span data-stu-id="299ef-115">For example, the [UnicodeEncoding](xref:System.Text.UnicodeEncoding) class checks all surrogates to make sure they constitute valid surrogate pairs.</span></span> <span data-ttu-id="299ef-116">Una coppia di surrogati è costituita da un carattere con un punto di codice compreso tra U+D800 e U+DBFF seguito da un carattere con un punto di codice compreso tra U+DC00 e U+DFFF. Una strategia di fallback determina come un codificatore gestisce i caratteri non validi o come un decodificatore gestisce i byte non validi.</span><span class="sxs-lookup"><span data-stu-id="299ef-116">(A surrogate pair consists of a character with a code point that ranges from U+D800 to U+DBFF followed by a character with a code point that ranges from U+DC00 to U+DFFF.) A fallback strategy determines how an encoder handles invalid characters or how a decoder handles invalid bytes.</span></span> 

> [!WARNING]
> <span data-ttu-id="299ef-117">Le classi di codifica in .NET consentono di archiviare e convertire i dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="299ef-117">The .NET encoding classes provide a way to store and convert character data.</span></span> <span data-ttu-id="299ef-118">Non devono essere usate per archiviare i dati binari in formato stringa.</span><span class="sxs-lookup"><span data-stu-id="299ef-118">They should not be used to store binary data in string form.</span></span> <span data-ttu-id="299ef-119">In base alla codifica usata, la conversione dei dati binari in formato stringa con le classi Encoding può introdurre un comportamento imprevisto e generare dati non accurati o danneggiati.</span><span class="sxs-lookup"><span data-stu-id="299ef-119">Depending on the encoding used, converting binary data to string format with the encoding classes can introduce unexpected behavior and produce inaccurate or corrupted data.</span></span> <span data-ttu-id="299ef-120">Per convertire i dati binari in un formato stringa, usare il metodo [Convert.ToBase64String](xref:System.Convert.ToBase64String(System.Byte[])).</span><span class="sxs-lookup"><span data-stu-id="299ef-120">To convert binary data to a string form, use the [Convert.ToBase64String](xref:System.Convert.ToBase64String(System.Byte[])) method.</span></span> 
 
<span data-ttu-id="299ef-121">.NET usa la codifica UTF-16, rappresentata dalla classe [UnicodeEncoding](xref:System.Text.UnicodeEncoding), per rappresentare i caratteri e le stringhe.</span><span class="sxs-lookup"><span data-stu-id="299ef-121">.NET uses the UTF-16 encoding (represented by the [UnicodeEncoding](xref:System.Text.UnicodeEncoding) class) to represent characters and strings.</span></span> <span data-ttu-id="299ef-122">Le applicazioni destinate a Common Language Runtime usano codificatori per eseguire il mapping di rappresentazioni di caratteri Unicode supportate da Common Language Runtime ad altri schemi di codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-122">Applications that target the common language runtime use encoders to map Unicode character representations supported by the common language runtime to other encoding schemes.</span></span> <span data-ttu-id="299ef-123">Usano i decodificatori per eseguire il mapping di caratteri da codifiche non Unicode a Unicode.</span><span class="sxs-lookup"><span data-stu-id="299ef-123">They use decoders to map characters from non-Unicode encodings to Unicode.</span></span>

<span data-ttu-id="299ef-124">Questo argomento include le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="299ef-124">This topic consists of the following sections:</span></span>

* [<span data-ttu-id="299ef-125">Codifiche in .NET</span><span class="sxs-lookup"><span data-stu-id="299ef-125">Encodings in .NET</span></span>](#encodings-in-net)

* [<span data-ttu-id="299ef-126">Selezione di una classe di codifica</span><span class="sxs-lookup"><span data-stu-id="299ef-126">Selecting an encoding class</span></span>](#selecting-an-encoding-class)

* [<span data-ttu-id="299ef-127">Uso di un oggetto di codifica</span><span class="sxs-lookup"><span data-stu-id="299ef-127">Using an encoding object</span></span>](#using-an-encoding-object)

* [<span data-ttu-id="299ef-128">Scelta di una strategia di fallback</span><span class="sxs-lookup"><span data-stu-id="299ef-128">Choosing a fallback strategy</span></span>](#choosing-a-fallback-strategy)

* [<span data-ttu-id="299ef-129">Implementazione di una strategia di fallback personalizzata</span><span class="sxs-lookup"><span data-stu-id="299ef-129">Implementing a custom fallback strategy</span></span>](#implementing-a-custom-fallback-strategy)

## <a name="encodings-in-net"></a><span data-ttu-id="299ef-130">Codifiche in .NET</span><span class="sxs-lookup"><span data-stu-id="299ef-130">Encodings in .NET</span></span>

<span data-ttu-id="299ef-131">Tutte le classi di codifica dei caratteri in .NET ereditano dalla classe [System.Text.Encoding](xref:System.Text.Encoding), una classe astratta che definisce le funzionalità comuni a tutte le codifiche dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="299ef-131">All character encoding classes in .NET inherit from the [System.Text.Encoding](xref:System.Text.Encoding) class, which is an abstract class that defines the functionality common to all character encodings.</span></span> <span data-ttu-id="299ef-132">Per accedere ai singoli oggetti di codifica implementati in .NET, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="299ef-132">To access the individual encoding objects implemented in .NET, do the following:</span></span>

* <span data-ttu-id="299ef-133">Usare le proprietà statiche della classe [Encoding](xref:System.Text.Encoding), che restituiscono oggetti che rappresentano le codifiche dei caratteri standard disponibili in .NET (ASCII, UTF-7, UTF-8, UTF-16 e UTF-32).</span><span class="sxs-lookup"><span data-stu-id="299ef-133">Use the static properties of the [Encoding](xref:System.Text.Encoding) class, which return objects that represent the standard character encodings available in .NET (ASCII, UTF-7, UTF-8, UTF-16, and UTF-32).</span></span> <span data-ttu-id="299ef-134">Ad esempio, la proprietà [Encoding.Unicode](xref:System.Text.Encoding.Unicode) restituisce un oggetto [UnicodeEncoding](xref:System.Text.UnicodeEncoding).</span><span class="sxs-lookup"><span data-stu-id="299ef-134">For example, the [Encoding.Unicode](xref:System.Text.Encoding.Unicode) property returns a [UnicodeEncoding](xref:System.Text.UnicodeEncoding) object.</span></span> <span data-ttu-id="299ef-135">Ogni oggetto usa il fallback di sostituzione per gestire le stringhe che non può codificare e i byte che non può decodificare.</span><span class="sxs-lookup"><span data-stu-id="299ef-135">Each object uses replacement fallback to handle strings that it cannot encode and bytes that it cannot decode.</span></span> <span data-ttu-id="299ef-136">Per altre informazioni, vedere la sezione [Fallback di sostituzione](#replacement-fallback).</span><span class="sxs-lookup"><span data-stu-id="299ef-136">(For more information, see the [Replacement fallback](#replacement-fallback) section.)</span></span>

* <span data-ttu-id="299ef-137">Chiamare il costruttore di classe della codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-137">Call the encoding's class constructor.</span></span> <span data-ttu-id="299ef-138">In questo modo è possibile creare istanze di oggetti per le codifiche ASCII, UTF-7, UTF-8, UTF-16 e UTF-32.</span><span class="sxs-lookup"><span data-stu-id="299ef-138">Objects for the ASCII, UTF-7, UTF-8, UTF-16, and UTF-32 encodings can be instantiated in this way.</span></span> <span data-ttu-id="299ef-139">Per impostazione predefinita, ogni oggetto usa il fallback di sostituzione per gestire le stringhe che non può codificare e i byte che non può decodificare, ma è possibile specificare che invece deve essere generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="299ef-139">By default, each object uses replacement fallback to handle strings that it cannot encode and bytes that it cannot decode, but you can specify that an exception should be thrown instead.</span></span> <span data-ttu-id="299ef-140">Per altre informazioni, vedere le sezioni [Fallback di sostituzione](#replacement-fallback) e [Fallback di eccezione](#exception-fallback).</span><span class="sxs-lookup"><span data-stu-id="299ef-140">(For more information, see the [Replacement fallback](#replacement-fallback) and [Exception fallback](#exception-fallback) sections.)</span></span>

* <span data-ttu-id="299ef-141">Chiamare il costruttore [Encoding.Encoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) e passargli un Integer che rappresenta la codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-141">Call the [Encoding.Encoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) constructor and pass it an integer that represents the encoding.</span></span> <span data-ttu-id="299ef-142">Gli oggetti di codifica standard usano il fallback di sostituzione e gli oggetti di codifica della tabella codici e Double Byte Character Set (DBCS) usano il fallback con mapping più appropriato per gestire le stringhe che non possono codificare e i byte che non possono decodificare.</span><span class="sxs-lookup"><span data-stu-id="299ef-142">Standard encoding objects use replacement fallback, and code page and double-byte character set (DBCS) encoding objects use best-fit fallback to handle strings that they cannot encode and bytes that they cannot decode.</span></span> <span data-ttu-id="299ef-143">Per altre informazioni, vedere la sezione [Fallback con mapping più appropriato](#best-fit-fallback).</span><span class="sxs-lookup"><span data-stu-id="299ef-143">(For more information, see the [Best-Fit fallback](#best-fit-fallback) section.)</span></span>

* <span data-ttu-id="299ef-144">Chiamare il metodo [Encoding.GetEncoding](xref:System.Text.Encoding.GetEncoding(System.Int32)), che restituisce qualsiasi codifica standard, della tabella codici o DBCS disponibile in .NET.</span><span class="sxs-lookup"><span data-stu-id="299ef-144">Call the [Encoding.GetEncoding](xref:System.Text.Encoding.GetEncoding(System.Int32)) method, which returns any standard, code page, or DBCS encoding available in .NET.</span></span> <span data-ttu-id="299ef-145">Gli overload consentono di specificare un oggetto di fallback sia per il codificatore che per il decodificatore.</span><span class="sxs-lookup"><span data-stu-id="299ef-145">Overloads let you specify a fallback object for both the encoder and the decoder.</span></span>

> [!NOTE]
> <span data-ttu-id="299ef-146">Lo standard Unicode assegna un punto di codice (un numero) e un nome a ciascun carattere in ogni script supportato.</span><span class="sxs-lookup"><span data-stu-id="299ef-146">The Unicode Standard assigns a code point (a number) and a name to each character in every supported script.</span></span> <span data-ttu-id="299ef-147">Ad esempio, il carattere "A" è rappresentato dal punto di codice U+0041 e dal nome "LATIN CAPITAL LETTER A".</span><span class="sxs-lookup"><span data-stu-id="299ef-147">For example, the character "A" is represented by the code point U+0041 and the name "LATIN CAPITAL LETTER A".</span></span> <span data-ttu-id="299ef-148">Le codifiche Unicode Transformation Format (UTF) definiscono i modi per codificare quel punto di codice in una sequenza di uno o più byte.</span><span class="sxs-lookup"><span data-stu-id="299ef-148">The Unicode Transformation Format (UTF) encodings define ways to encode that code point into a sequence of one or more bytes.</span></span> <span data-ttu-id="299ef-149">Uno schema di codifica Unicode semplifica lo sviluppo di applicazioni internazionali, perché consente di rappresentare in una sola codifica i caratteri di qualsiasi set di caratteri.</span><span class="sxs-lookup"><span data-stu-id="299ef-149">A Unicode encoding scheme simplifies world-ready application development because it allows characters from any character set to be represented in a single encoding.</span></span> <span data-ttu-id="299ef-150">Gli sviluppatori di applicazioni non devono più tenere traccia dello schema di codifica usato per produrre i caratteri per una lingua o un sistema di scrittura specifico e i dati possono essere condivisi tra i sistemi a livello internazionale senza essere danneggiati.</span><span class="sxs-lookup"><span data-stu-id="299ef-150">Application developers no longer have to keep track of the encoding scheme that was used to produce characters for a specific language or writing system, and data can be shared among systems internationally without being corrupted.</span></span>
>
>  <span data-ttu-id="299ef-151">.NET supporta tre codifiche definite dallo standard Unicode: UTF-8, UTF-16 e UTF-32.</span><span class="sxs-lookup"><span data-stu-id="299ef-151">.NET supports three encodings defined by the Unicode standard: UTF-8, UTF-16, and UTF-32.</span></span> <span data-ttu-id="299ef-152">Per altre informazioni, vedere lo standard Unicode nella [home page di Unicode](http://www.unicode.org/).</span><span class="sxs-lookup"><span data-stu-id="299ef-152">For more information, see The Unicode Standard at the [Unicode](http://www.unicode.org/) home page.</span></span>
 
<span data-ttu-id="299ef-153">.NET supporta i sistemi di codifica dei caratteri elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="299ef-153">.NET supports the character encoding systems listed in the following table.</span></span>

<span data-ttu-id="299ef-154">Codifica</span><span class="sxs-lookup"><span data-stu-id="299ef-154">Encoding</span></span> | <span data-ttu-id="299ef-155">Classe</span><span class="sxs-lookup"><span data-stu-id="299ef-155">Class</span></span> | <span data-ttu-id="299ef-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="299ef-156">Description</span></span> | <span data-ttu-id="299ef-157">Vantaggi/Svantaggi</span><span class="sxs-lookup"><span data-stu-id="299ef-157">Advantages/disadvantages</span></span>
-------- | ----- | ----------- | ------------------------ 
<span data-ttu-id="299ef-158">ASCII</span><span class="sxs-lookup"><span data-stu-id="299ef-158">ASCII</span></span> | [<span data-ttu-id="299ef-159">ASCIIEncoding</span><span class="sxs-lookup"><span data-stu-id="299ef-159">ASCIIEncoding</span></span>](xref:System.Text.ASCIIEncoding) | <span data-ttu-id="299ef-160">Codifica un intervallo limitato di caratteri usando i sette bit più bassi di un byte.</span><span class="sxs-lookup"><span data-stu-id="299ef-160">Encodes a limited range of characters by using the lower seven bits of a byte.</span></span> | <span data-ttu-id="299ef-161">Poiché questa codifica supporta solo i valori dei caratteri compresi tra U+0000 e U+007F, nella maggior parte dei casi non è adatta per le applicazioni internazionalizzate.</span><span class="sxs-lookup"><span data-stu-id="299ef-161">Because this encoding only supports character values from U+0000 through U+007F, in most cases it is inadequate for internationalized applications.</span></span>
<span data-ttu-id="299ef-162">UTF-7</span><span class="sxs-lookup"><span data-stu-id="299ef-162">UTF-7</span></span> | [<span data-ttu-id="299ef-163">UTF7Encoding</span><span class="sxs-lookup"><span data-stu-id="299ef-163">UTF7Encoding</span></span>](xref:System.Text.UTF7Encoding) | <span data-ttu-id="299ef-164">Rappresenta i caratteri come sequenze di caratteri ASCII a 7 bit.</span><span class="sxs-lookup"><span data-stu-id="299ef-164">Represents characters as sequences of 7-bit ASCII characters.</span></span> <span data-ttu-id="299ef-165">I caratteri Unicode non ASCII sono rappresentati da una sequenza di escape di caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="299ef-165">Non-ASCII Unicode characters are represented by an escape sequence of ASCII characters.</span></span> | <span data-ttu-id="299ef-166">UTF-7 supporta protocolli di newsgroup e di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="299ef-166">UTF-7 supports protocols such as e-mail and newsgroup protocols.</span></span> <span data-ttu-id="299ef-167">UTF-7 non è tuttavia particolarmente sicura o affidabile.</span><span class="sxs-lookup"><span data-stu-id="299ef-167">However, UTF-7 is not particularly secure or robust.</span></span> <span data-ttu-id="299ef-168">In alcuni casi, la modifica di un bit può alterare radicalmente l'interpretazione di un'intera stringa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="299ef-168">In some cases, changing one bit can radically alter the interpretation of an entire UTF-7 string.</span></span> <span data-ttu-id="299ef-169">In altri casi, stringhe UTF-7 diverse possono codificare lo stesso testo.</span><span class="sxs-lookup"><span data-stu-id="299ef-169">In other cases, different UTF-7 strings can encode the same text.</span></span> <span data-ttu-id="299ef-170">Per le sequenze che includono caratteri non ASCII, UTF-7 richiede più spazio di UTF-8 e la codifica/decodifica è più lenta.</span><span class="sxs-lookup"><span data-stu-id="299ef-170">For sequences that include non-ASCII characters, UTF-7 requires more space than UTF-8, and encoding/decoding is slower.</span></span> <span data-ttu-id="299ef-171">Di conseguenza, è consigliabile usare UTF-8 anziché UTF-7, se possibile.</span><span class="sxs-lookup"><span data-stu-id="299ef-171">Consequently, you should use UTF-8 instead of UTF-7 if possible.</span></span>
<span data-ttu-id="299ef-172">UTF-8</span><span class="sxs-lookup"><span data-stu-id="299ef-172">UTF-8</span></span> | [<span data-ttu-id="299ef-173">UTF8Encoding</span><span class="sxs-lookup"><span data-stu-id="299ef-173">UTF8Encoding</span></span>](xref:System.Text.UTF8Encoding) | <span data-ttu-id="299ef-174">Rappresenta ogni punto di codice Unicode come sequenza che include da uno a quattro byte.</span><span class="sxs-lookup"><span data-stu-id="299ef-174">Represents each Unicode code point as a sequence of one to four bytes.</span></span> | <span data-ttu-id="299ef-175">UTF-8 supporta dimensioni dati a 8 bit e funziona bene con molti sistemi operativi esistenti.</span><span class="sxs-lookup"><span data-stu-id="299ef-175">UTF-8 supports 8-bit data sizes and works well with many existing operating systems.</span></span> <span data-ttu-id="299ef-176">Per l'intervallo di caratteri ASCII, UTF-8 è identica alla codifica ASCII e consente un più ampio set di caratteri.</span><span class="sxs-lookup"><span data-stu-id="299ef-176">For the ASCII range of characters, UTF-8 is identical to ASCII encoding and allows a broader set of characters.</span></span> <span data-ttu-id="299ef-177">Tuttavia, per gli script in cinese-giapponese-coreano (CJK), UTF-8 può richiedere tre byte per ogni carattere e potrebbe generare dimensioni dati maggiori di UTF-16.</span><span class="sxs-lookup"><span data-stu-id="299ef-177">However, for Chinese-Japanese-Korean (CJK) scripts, UTF-8 can require three bytes for each character, and can potentially cause larger data sizes than UTF-16.</span></span> <span data-ttu-id="299ef-178">Si noti che a volte la quantità di dati ASCII, ad esempio di tag HTML, giustifica l'aumento delle dimensioni per la gamma CJK.</span><span class="sxs-lookup"><span data-stu-id="299ef-178">Note that sometimes the amount of ASCII data, such as HTML tags, justifies the increased size for the CJK range.</span></span>
<span data-ttu-id="299ef-179">UTF-16</span><span class="sxs-lookup"><span data-stu-id="299ef-179">UTF-16</span></span> | [<span data-ttu-id="299ef-180">UnicodeEncoding</span><span class="sxs-lookup"><span data-stu-id="299ef-180">UnicodeEncoding</span></span>](xref:System.Text.UnicodeEncoding) | <span data-ttu-id="299ef-181">Rappresenta ogni punto di codice Unicode come sequenza di uno o due Integer a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="299ef-181">Represents each Unicode code point as a sequence of one or two 16-bit integers.</span></span> <span data-ttu-id="299ef-182">I caratteri Unicode più comuni richiedono un solo punto di codice UTF-16, anche se i caratteri supplementari Unicode (U+10000 e successivi) richiedono due punti di codice surrogati UTF-16.</span><span class="sxs-lookup"><span data-stu-id="299ef-182">Most common Unicode characters require only one UTF-16 code point, although Unicode supplementary characters (U+10000 and greater) require two UTF-16 surrogate code points.</span></span> <span data-ttu-id="299ef-183">Sono supportati sia ordini dei byte little-endian che big-endian.</span><span class="sxs-lookup"><span data-stu-id="299ef-183">Both little-endian and big-endian byte orders are supported.</span></span> | <span data-ttu-id="299ef-184">La codifica UTF-16 viene usata da Common Language Runtime per rappresentare i valori Char e String e dal sistema operativo Windows per rappresentare i valori WCHAR.</span><span class="sxs-lookup"><span data-stu-id="299ef-184">UTF-16 encoding is used by the common language runtime to represent Char and String values, and it is used by the Windows operating system to represent WCHAR values.</span></span>
<span data-ttu-id="299ef-185">UTF-32</span><span class="sxs-lookup"><span data-stu-id="299ef-185">UTF-32</span></span> | [<span data-ttu-id="299ef-186">UTF32Encoding</span><span class="sxs-lookup"><span data-stu-id="299ef-186">UTF32Encoding</span></span>](xref:System.Text.UTF32Encoding) | <span data-ttu-id="299ef-187">Rappresenta ogni punto di codice Unicode come Integer a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="299ef-187">Represents each Unicode code point as a 32-bit integer.</span></span> <span data-ttu-id="299ef-188">Sono supportati sia ordini dei byte little-endian che big-endian.</span><span class="sxs-lookup"><span data-stu-id="299ef-188">Both little-endian and big-endian byte orders are supported.</span></span> | <span data-ttu-id="299ef-189">La codifica UTF-32 viene usata quando le applicazioni vogliono evitare il comportamento dei punti di codice surrogati della codifica UTF-16 in sistemi operativi per cui lo spazio codificato è estremamente importante.</span><span class="sxs-lookup"><span data-stu-id="299ef-189">UTF-32 encoding is used when applications want to avoid the surrogate code point behavior of UTF-16 encoding on operating systems for which encoded space is too important.</span></span> <span data-ttu-id="299ef-190">I singoli glifi visualizzati su uno schermo possono comunque essere codificati con più di un carattere UTF-32.</span><span class="sxs-lookup"><span data-stu-id="299ef-190">Single glyphs rendered on a display can still be encoded with more than one UTF-32 character.</span></span>

<span data-ttu-id="299ef-191">Queste codifiche consentono di lavorare con i caratteri Unicode e con le codifiche più comunemente usate nelle applicazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="299ef-191">These encodings enable you to work with Unicode characters as well as with encodings that are most commonly used in legacy applications.</span></span> <span data-ttu-id="299ef-192">È anche possibile creare una codifica personalizzata definendo una classe che deriva da [Encoding](xref:System.Text.Encoding) ed eseguendo l'override dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="299ef-192">In addition, you can create a custom encoding by defining a class that derives from [Encoding](xref:System.Text.Encoding) and overriding its members.</span></span>

> [!NOTE]
> <span data-ttu-id="299ef-193">Per impostazione predefinita, .NET Core non rende disponibili le codifiche delle tabelle codici diverse dalla tabella codice 28591 e le codifiche Unicode, ad esempio UTF-8 e UTF-16.</span><span class="sxs-lookup"><span data-stu-id="299ef-193">By default, .NET Core does not make available any code page encodings other than code page 28591 and the Unicode encodings, such as UTF-8 and UTF-16.</span></span> <span data-ttu-id="299ef-194">Tuttavia, è possibile aggiungere all'app le codifiche delle tabelle codici presenti nelle app di Windows standard destinate a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="299ef-194">However, you can add the code page encodings found in standard Windows apps that target the .NET Framework to your app.</span></span> <span data-ttu-id="299ef-195">Per informazioni complete, vedere l'argomento [EncodingProvider](xref:System.Text.EncodingProvider).</span><span class="sxs-lookup"><span data-stu-id="299ef-195">For complete information, see the [EncodingProvider](xref:System.Text.EncodingProvider) topic.</span></span> 

## <a name="selecting-an-encoding-class"></a><span data-ttu-id="299ef-196">Selezione di una classe di codifica</span><span class="sxs-lookup"><span data-stu-id="299ef-196">Selecting an Encoding class</span></span>

<span data-ttu-id="299ef-197">Se è possibile scegliere la codifica che verrà usata dall'applicazione, è consigliabile usare una codifica Unicode, preferibilmente [UTF8Encoding](xref:System.Text.UTF8Encoding) o [UnicodeEncoding](xref:System.Text.UnicodeEncoding).</span><span class="sxs-lookup"><span data-stu-id="299ef-197">If you have the opportunity to choose the encoding to be used by your application, you should use a Unicode encoding, preferably either [UTF8Encoding](xref:System.Text.UTF8Encoding) or [UnicodeEncoding](xref:System.Text.UnicodeEncoding).</span></span> <span data-ttu-id="299ef-198">.NET supporta anche una terza codifica Unicode, vale a dire [UTF32Encoding](xref:System.Text.UTF32Encoding).</span><span class="sxs-lookup"><span data-stu-id="299ef-198">(.NET also supports a third Unicode encoding, [UTF32Encoding](xref:System.Text.UTF32Encoding).)</span></span> 

<span data-ttu-id="299ef-199">Se si prevede di usare una codifica ASCII ([ASCIIEncoding](xref:System.Text.ASCIIEncoding)), scegliere invece [UTF8Encoding](xref:System.Text.UTF8Encoding).</span><span class="sxs-lookup"><span data-stu-id="299ef-199">If you are planning to use an ASCII encoding ([ASCIIEncoding](xref:System.Text.ASCIIEncoding)), choose [UTF8Encoding](xref:System.Text.UTF8Encoding) instead.</span></span> <span data-ttu-id="299ef-200">Le due codifiche sono identiche per il set di caratteri ASCII, ma [UTF8Encoding](xref:System.Text.UTF8Encoding) offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="299ef-200">The two encodings are identical for the ASCII character set, but [UTF8Encoding](xref:System.Text.UTF8Encoding) has the following advantages:</span></span> 

* <span data-ttu-id="299ef-201">Può rappresentare tutti i caratteri Unicode, mentre [ASCIIEncoding](xref:System.Text.ASCIIEncoding) supporta solo i valori di caratteri Unicode compresi tra U+0000 e U+007F.</span><span class="sxs-lookup"><span data-stu-id="299ef-201">It can represent every Unicode character, whereas [ASCIIEncoding](xref:System.Text.ASCIIEncoding) supports only the Unicode character values between U+0000 and U+007F.</span></span>

* <span data-ttu-id="299ef-202">Fornisce il rilevamento errori e una migliore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="299ef-202">It provides error detection and better security.</span></span>

* <span data-ttu-id="299ef-203">È stata ottimizzata per essere il più veloce possibile e dovrebbe essere più veloce di qualsiasi altra codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-203">It has been tuned to be as fast as possible and should be faster than any other encoding.</span></span> <span data-ttu-id="299ef-204">Anche per il contenuto interamente ASCII, le operazioni eseguite con [UTF8Encoding](xref:System.Text.UTF8Encoding) sono più veloci delle operazioni eseguite con [ASCIIEncoding](xref:System.Text.ASCIIEncoding).</span><span class="sxs-lookup"><span data-stu-id="299ef-204">Even for content that is entirely ASCII, operations performed with [UTF8Encoding](xref:System.Text.UTF8Encoding) are faster than operations performed with [ASCIIEncoding](xref:System.Text.ASCIIEncoding).</span></span>

<span data-ttu-id="299ef-205">È consigliabile usare [ASCIIEncoding](xref:System.Text.ASCIIEncoding) solo per le applicazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="299ef-205">You should consider using [ASCIIEncoding](xref:System.Text.ASCIIEncoding) only for legacy applications.</span></span> <span data-ttu-id="299ef-206">Anche per le applicazioni legacy, [UTF8Encoding](xref:System.Text.UTF8Encoding) potrebbe essere tuttavia una scelta migliore per i motivi seguenti, presupponendo le impostazioni predefinite:</span><span class="sxs-lookup"><span data-stu-id="299ef-206">However, even for legacy applications, [UTF8Encoding](xref:System.Text.UTF8Encoding) might be a better choice for the following reasons (assuming default settings):</span></span>

* <span data-ttu-id="299ef-207">Se l'applicazione include contenuto non esclusivamente ASCII e lo codifica con [ASCIIEncoding](xref:System.Text.ASCIIEncoding), ogni carattere non ASCII viene codificato come punto interrogativo (?).</span><span class="sxs-lookup"><span data-stu-id="299ef-207">If your application has content that is not strictly ASCII and encodes it with [ASCIIEncoding](xref:System.Text.ASCIIEncoding), each non-ASCII character encodes as a question mark (?).</span></span> <span data-ttu-id="299ef-208">Se l'applicazione quindi decodifica questi dati, le informazioni vengono perse.</span><span class="sxs-lookup"><span data-stu-id="299ef-208">If the application then decodes this data, the information is lost.</span></span>


* <span data-ttu-id="299ef-209">Se l'applicazione include contenuto non esclusivamente ASCII e lo codifica con [UTF8Encoding](xref:System.Text.UTF8Encoding), il risultato appare incomprensibile se interpretato come ASCII.</span><span class="sxs-lookup"><span data-stu-id="299ef-209">If your application has content that is not strictly ASCII and encodes it with [UTF8Encoding](xref:System.Text.UTF8Encoding), the result seems unintelligible if interpreted as ASCII.</span></span> <span data-ttu-id="299ef-210">Tuttavia, se l'applicazione usa poi un decodificatore UTF-8 per decodificare questi dati, i dati eseguono correttamente un round trip.</span><span class="sxs-lookup"><span data-stu-id="299ef-210">However, if the application then uses a UTF-8 decoder to decode this data, the data performs a round trip successfully.</span></span>

<span data-ttu-id="299ef-211">In un'applicazione Web, i caratteri inviati al client in risposta a una richiesta Web dovrebbero rispecchiare la codifica usata nel client.</span><span class="sxs-lookup"><span data-stu-id="299ef-211">In a web application, characters sent to the client in response to a web request should reflect the encoding used on the client.</span></span> <span data-ttu-id="299ef-212">Nella maggior parte dei casi, è consigliabile impostare la proprietà [HttpResponse.ContentEncoding](xref:System.Net.HttpResponseHeader.ContentEncoding) sul valore restituito dalla proprietà [HttpRequestHeader.ContentEncoding](xref:System.Net.HttpRequestHeader.ContentEncoding) per visualizzare il testo nella codifica prevista dall'utente.</span><span class="sxs-lookup"><span data-stu-id="299ef-212">In most cases, you should set the [HttpResponse.ContentEncoding](xref:System.Net.HttpResponseHeader.ContentEncoding) property to the value returned by the [HttpRequestHeader.ContentEncoding](xref:System.Net.HttpRequestHeader.ContentEncoding) property to display text in the encoding that the user expects.</span></span>

## <a name="using-an-encoding-object"></a><span data-ttu-id="299ef-213">Uso di un oggetto di codifica</span><span class="sxs-lookup"><span data-stu-id="299ef-213">Using an encoding object</span></span>

<span data-ttu-id="299ef-214">Un codificatore converte una stringa di caratteri (per lo più caratteri Unicode) nell'equivalente numerico (byte).</span><span class="sxs-lookup"><span data-stu-id="299ef-214">An encoder converts a string of characters (most commonly, Unicode characters) to its numeric (byte) equivalent.</span></span> <span data-ttu-id="299ef-215">Ad esempio, è possibile usare un codificatore ASCII per convertire i caratteri Unicode in ASCII e poterli visualizzare nella console.</span><span class="sxs-lookup"><span data-stu-id="299ef-215">For example, you might use an ASCII encoder to convert Unicode characters to ASCII so that they can be displayed at the console.</span></span> <span data-ttu-id="299ef-216">Per eseguire la conversione, chiamare il metodo [Encoding.GetBytes](xref:System.Text.Encoding.GetBytes(System.Char[])).</span><span class="sxs-lookup"><span data-stu-id="299ef-216">To perform the conversion, you call the [Encoding.GetBytes](xref:System.Text.Encoding.GetBytes(System.Char[])) method.</span></span> <span data-ttu-id="299ef-217">Per determinare il numero di byte necessari per archiviare i caratteri codificati prima di eseguire la codifica, è possibile chiamare il metodo [GetByteCount](xref:System.Text.Encoding.GetByteCount(System.Char[])).</span><span class="sxs-lookup"><span data-stu-id="299ef-217">If you want to determine how many bytes are needed to store the encoded characters before performing the encoding, you can call the [GetByteCount](xref:System.Text.Encoding.GetByteCount(System.Char[])) method.</span></span>

<span data-ttu-id="299ef-218">L'esempio seguente usa una singola matrice di byte per codificare le stringhe in due operazioni distinte.</span><span class="sxs-lookup"><span data-stu-id="299ef-218">The following example uses a single byte array to encode strings in two separate operations.</span></span> <span data-ttu-id="299ef-219">Gestisce un indice che indica la posizione iniziale nella matrice di byte per il set successivo di byte con codifica ASCII.</span><span class="sxs-lookup"><span data-stu-id="299ef-219">It maintains an index that indicates the starting position in the byte array for the next set of ASCII-encoded bytes.</span></span> <span data-ttu-id="299ef-220">Chiama il metodo [ASCIIEncoding.GetByteCount(String)](xref:System.Text.ASCIIEncoding.GetByteCount(System.String)) per assicurarsi che la matrice di byte sia grande abbastanza da contenere la stringa codificata.</span><span class="sxs-lookup"><span data-stu-id="299ef-220">It calls the [ASCIIEncoding.GetByteCount(String)](xref:System.Text.ASCIIEncoding.GetByteCount(System.String)) method to ensure that the byte array is large enough to accommodate the encoded string.</span></span> <span data-ttu-id="299ef-221">Chiama poi il metodo [ASCIIEncoding.GetBytes(String, Int32, Int32, Byte[], Int32)](xref:System.Text.ASCIIEncoding.GetBytes(System.Char[],System.Int32,System.Int32,System.Byte[],System.Int32)) per codificare i caratteri nella stringa.</span><span class="sxs-lookup"><span data-stu-id="299ef-221">It then calls the [ASCIIEncoding.GetBytes(String, Int32, Int32, Byte[], Int32)](xref:System.Text.ASCIIEncoding.GetBytes(System.Char[],System.Int32,System.Int32,System.Byte[],System.Int32)) method to encode the characters in the string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings= { "This is the first sentence. ", 
                          "This is the second sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;

      // Create array of adequate size.
      byte[] bytes = new byte[49];
      // Create index for current position of array.
      int index = 0;

      Console.WriteLine("Strings to encode:");
      foreach (var stringValue in strings) {
         Console.WriteLine("   {0}", stringValue);

         int count = asciiEncoding.GetByteCount(stringValue);
         if (count + index >=  bytes.Length)
            Array.Resize(ref bytes, bytes.Length + 50);

         int written = asciiEncoding.GetBytes(stringValue, 0, 
                                              stringValue.Length, 
                                              bytes, index);    

         index = index + written; 
      } 
      Console.WriteLine("\nEncoded bytes:");
      Console.WriteLine("{0}", ShowByteValues(bytes, index));
      Console.WriteLine();

      // Decode Unicode byte array to a string.
      string newString = asciiEncoding.GetString(bytes, 0, index);
      Console.WriteLine("Decoded: {0}", newString);
   }

   private static string ShowByteValues(byte[] bytes, int last ) 
   {
      string returnString = "   ";
      for (int ctr = 0; ctr <= last - 1; ctr++) {
         if (ctr % 20 == 0)
            returnString += "\n   ";
         returnString += String.Format("{0:X2} ", bytes[ctr]);
      }
      return returnString;
   }
}
// The example displays the following output:
//       Strings to encode:
//          This is the first sentence.
//          This is the second sentence.
//       
//       Encoded bytes:
//       
//          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
//          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
//       
//       Decoded: This is the first sentence. This is the second sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII

      ' Create array of adequate size.
      Dim bytes(50) As Byte
      ' Create index for current position of array.
      Dim index As Integer = 0

      Console.WriteLine("Strings to encode:")
      For Each stringValue In strings
         Console.WriteLine("   {0}", stringValue)

         Dim count As Integer = asciiEncoding.GetByteCount(stringValue)
         If count + index >=  bytes.Length Then
            Array.Resize(bytes, bytes.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetBytes(stringValue, 0, 
                                                         stringValue.Length, 
                                                         bytes, index)    

         index = index + written 
      Next 
      Console.WriteLine()
      Console.WriteLine("Encoded bytes:")
      Console.WriteLine("{0}", ShowByteValues(bytes, index))
      Console.WriteLine()

      ' Decode Unicode byte array to a string.
      Dim newString As String = asciiEncoding.GetString(bytes, 0, index)
      Console.WriteLine("Decoded: {0}", newString)
   End Sub

   Private Function ShowByteValues(bytes As Byte(), last As Integer) As String
      Dim returnString As String = "   "
      For ctr As Integer = 0 To last - 1
         If ctr Mod 20 = 0 Then returnString += vbCrLf + "   "
         returnString += String.Format("{0:X2} ", bytes(ctr))
      Next
      Return returnString
   End Function
End Module
' The example displays the following output:
'       Strings to encode:
'          This is the first sentence.
'          This is the second sentence.
'       
'       Encoded bytes:
'       
'          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
'          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
'       
'       Decoded: This is the first sentence. This is the second sentence.
```

<span data-ttu-id="299ef-222">Un decodificatore converte una matrice di byte che rispecchia una particolare codifica dei caratteri in un set di caratteri, in una matrice di caratteri o in una stringa.</span><span class="sxs-lookup"><span data-stu-id="299ef-222">A decoder converts a byte array that reflects a particular character encoding into a set of characters, either in a character array or in a string.</span></span> <span data-ttu-id="299ef-223">Per decodificare una matrice di byte in una matrice di caratteri, chiamare il metodo [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])).</span><span class="sxs-lookup"><span data-stu-id="299ef-223">To decode a byte array into a character array, you call the [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) method.</span></span> <span data-ttu-id="299ef-224">Per decodificare una matrice di byte in una stringa, chiamare il metodo [GetString](xref:System.Text.Encoding.GetString(System.Byte[])).</span><span class="sxs-lookup"><span data-stu-id="299ef-224">To decode a byte array into a string, you call the [GetString](xref:System.Text.Encoding.GetString(System.Byte[])) method.</span></span> <span data-ttu-id="299ef-225">Per determinare il numero di caratteri necessari per archiviare i byte decodificati prima di eseguire la decodifica, è possibile chiamare il metodo [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])).</span><span class="sxs-lookup"><span data-stu-id="299ef-225">If you want to determine how many characters are needed to store the decoded bytes before performing the decoding, you can call the [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])) method.</span></span>

<span data-ttu-id="299ef-226">L'esempio seguente codifica tre stringhe e quindi le decodifica in una singola matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="299ef-226">The following example encodes three strings and then decodes them into a single array of characters.</span></span> <span data-ttu-id="299ef-227">Gestisce un indice che indica la posizione iniziale nella matrice di caratteri per il set successivo di caratteri decodificati.</span><span class="sxs-lookup"><span data-stu-id="299ef-227">It maintains an index that indicates the starting position in the character array for the next set of decoded characters.</span></span> <span data-ttu-id="299ef-228">Chiama il metodo [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])) per assicurarsi che la matrice di caratteri sia grande abbastanza da contenere tutti i caratteri decodificati.</span><span class="sxs-lookup"><span data-stu-id="299ef-228">It calls the [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])) method to ensure that the character array is large enough to accommodate all the decoded characters.</span></span> <span data-ttu-id="299ef-229">Chiama poi il metodo [ASCIIEncoding.GetChars(Byte[], Int32, Int32, Char[], Int32)](xref:System.Text.ASCIIEncoding.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) per decodificare la matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="299ef-229">It then calls the [ASCIIEncoding.GetChars(Byte[], Int32, Int32, Char[], Int32)](xref:System.Text.ASCIIEncoding.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) method to decode the byte array.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings = { "This is the first sentence. ", 
                           "This is the second sentence. ",
                           "This is the third sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;
      // Array to hold encoded bytes.
      byte[] bytes;
      // Array to hold decoded characters.
      char[] chars = new char[50];
      // Create index for current position of character array.
      int index = 0;     

      foreach (var stringValue in strings) {
         Console.WriteLine("String to Encode: {0}", stringValue);
         // Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue);
         // Display the encoded bytes.
         Console.Write("Encoded bytes: ");
         for (int ctr = 0; ctr < bytes.Length; ctr++)
            Console.Write(" {0}{1:X2}", 
                          ctr % 20 == 0 ? Environment.NewLine : "", 
                          bytes[ctr]);
         Console.WriteLine();

         // Decode the bytes to a single character array.
         int count = asciiEncoding.GetCharCount(bytes);
         if (count + index >=  chars.Length)
            Array.Resize(ref chars, chars.Length + 50);

         int written = asciiEncoding.GetChars(bytes, 0, 
                                              bytes.Length, 
                                              chars, index);              
         index = index + written;
         Console.WriteLine();       
      }

      // Instantiate a single string containing the characters.
      string decodedString = new string(chars, 0, index - 1);
      Console.WriteLine("Decoded string: ");
      Console.WriteLine(decodedString);
   }
}
// The example displays the following output:
//    String to Encode: This is the first sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the second sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
//    65 6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the third sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    Decoded string:
//    This is the first sentence. This is the second sentence. This is the third sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. ",
                                  "This is the third sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII
      ' Array to hold encoded bytes.
      Dim bytes() As Byte
      ' Array to hold decoded characters.
      Dim chars(50) As Char
      ' Create index for current position of character array.
      Dim index As Integer     

      For Each stringValue In strings
         Console.WriteLine("String to Encode: {0}", stringValue)
         ' Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue)
         ' Display the encoded bytes.
         Console.Write("Encoded bytes: ")
         For ctr As Integer = 0 To bytes.Length - 1
            Console.Write(" {0}{1:X2}", If(ctr Mod 20 = 0, vbCrLf, ""), 
                                        bytes(ctr))
         Next         
         Console.WriteLine()

         ' Decode the bytes to a single character array.
         Dim count As Integer = asciiEncoding.GetCharCount(bytes)
         If count + index >=  chars.Length Then
            Array.Resize(chars, chars.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetChars(bytes, 0, 
                                                         bytes.Length, 
                                                         chars, index)              
         index = index + written
         Console.WriteLine()       
      Next

      ' Instantiate a single string containing the characters.
      Dim decodedString As New String(chars, 0, index - 1)
      Console.WriteLine("Decoded string: ")
      Console.WriteLine(decodedString)
   End Sub
End Module
' The example displays the following output:
'    String to Encode: This is the first sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the second sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
'    65 6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the third sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    Decoded string:
'    This is the first sentence. This is the second sentence. This is the third sentence.
```

<span data-ttu-id="299ef-230">I metodi di codifica e di decodifica di una classe derivata da [Encoding](xref:System.Text.Encoding) sono progettati per funzionare su un set completo di dati, ovvero tutti i dati da codificare o decodificare vengono specificati in una singola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="299ef-230">The encoding and decoding methods of a class derived from [Encoding](xref:System.Text.Encoding) are designed to work on a complete set of data; that is, all the data to be encoded or decoded is supplied in a single method call.</span></span> <span data-ttu-id="299ef-231">In alcuni casi, tuttavia, i dati sono disponibili in un flusso e i dati da codificare o decodificare potrebbero essere disponibili solo in operazioni di lettura distinte.</span><span class="sxs-lookup"><span data-stu-id="299ef-231">However, in some cases, data is available in a stream, and the data to be encoded or decoded may be available only from separate read operations.</span></span> <span data-ttu-id="299ef-232">Ciò richiede che l'operazione di codifica o decodifica ricordi qualsiasi stato salvato dalla chiamata precedente.</span><span class="sxs-lookup"><span data-stu-id="299ef-232">This requires the encoding or decoding operation to remember any saved state from its previous invocation.</span></span> <span data-ttu-id="299ef-233">I metodi delle classi derivate da [Encoder](xref:System.Text.Encoder) e [Decoder](xref:System.Text.Decoder) possono gestire le operazioni di codifica e decodifica che comprendono più chiamate ai metodi.</span><span class="sxs-lookup"><span data-stu-id="299ef-233">Methods of classes derived from [Encoder](xref:System.Text.Encoder) and [Decoder](xref:System.Text.Decoder) are able to handle encoding and decoding operations that span multiple method calls.</span></span>

<span data-ttu-id="299ef-234">Un oggetto [Encoder](xref:System.Text.Encoder) per una particolare codifica è disponibile nella proprietà [Encoding.GetEncoder](xref:System.Text.Encoding.GetEncoder) di tale codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-234">An [Encoder](xref:System.Text.Encoder) object for a particular encoding is available from that encoding's [Encoding.GetEncoder](xref:System.Text.Encoding.GetEncoder) property.</span></span> <span data-ttu-id="299ef-235">Un oggetto [Decoder](xref:System.Text.Decoder) per una particolare codifica è disponibile nella proprietà [Encoding.GetDecoder](xref:System.Text.Encoding.GetDecoder) di tale codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-235">A [Decoder](xref:System.Text.Decoder) object for a particular encoding is available from that encoding's [Encoding.GetDecoder](xref:System.Text.Encoding.GetDecoder) property.</span></span> <span data-ttu-id="299ef-236">Per le operazioni di decodifica, si noti che le classi derivate da [Decoder](xref:System.Text.Decoder) includono un metodo [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)), ma non hanno uni un metodo corrispondente a [Encoding.GetString](xref:System.Text.Encoding.GetString(System.Byte[])).</span><span class="sxs-lookup"><span data-stu-id="299ef-236">For decoding operations, note that classes derived from [Decoder](xref:System.Text.Decoder) include a [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) method, but they do not have a method that corresponds to [Encoding.GetString](xref:System.Text.Encoding.GetString(System.Byte[])).</span></span>

<span data-ttu-id="299ef-237">L'esempio seguente illustra la differenza tra l'uso dei metodi [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) e [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) per la decodifica di una matrice di byte Unicode.</span><span class="sxs-lookup"><span data-stu-id="299ef-237">The following example illustrates the difference between using the [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) and [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) methods for decoding a Unicode byte array.</span></span> <span data-ttu-id="299ef-238">L'esempio codifica in un file una stringa che contiene alcuni caratteri Unicode e quindi usa i due metodi di decodifica per decodificarli dieci byte alla volta.</span><span class="sxs-lookup"><span data-stu-id="299ef-238">The example encodes a string that contains some Unicode characters to a file, and then uses the two decoding methods to decode them ten bytes at a time.</span></span> <span data-ttu-id="299ef-239">Una coppia di surrogati presente nel decimo e nell'undicesimo byte viene decodificata in chiamate ai metodi distinte.</span><span class="sxs-lookup"><span data-stu-id="299ef-239">Because a surrogate pair occurs in the tenth and eleventh bytes, it is decoded in separate method calls.</span></span> <span data-ttu-id="299ef-240">Come specificato dall'output, il metodo [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) non può decodificare i byte e li sostituisce invece con +FFFD (REPLACEMENT CHARACTER).</span><span class="sxs-lookup"><span data-stu-id="299ef-240">As the output shows, the [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) method is not able to correctly decode the bytes and instead replaces them with U+FFFD (REPLACEMENT CHARACTER).</span></span> <span data-ttu-id="299ef-241">D'altra parte, il metodo [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) può decodificare la matrice di byte per ottenere la stringa originale.</span><span class="sxs-lookup"><span data-stu-id="299ef-241">On the other hand, the [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) method is able to successfully decode the byte array to get the original string.</span></span>

```csharp
using System;
using System.IO;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Use default replacement fallback for invalid encoding.
      UnicodeEncoding enc = new UnicodeEncoding(true, false, false);

      // Define a string with various Unicode characters.
      string str1 = "AB YZ 19 \uD800\udc05 \u00e4"; 
      str1 += "Unicode characters. \u00a9 \u010C s \u0062\u0308"; 
      Console.WriteLine("Created original string...\n");

      // Convert string to byte array.                     
      byte[] bytes = enc.GetBytes(str1);

      FileStream fs = File.Create(@".\characters.bin");
      BinaryWriter bw = new BinaryWriter(fs);
      bw.Write(bytes);
      bw.Close();

      // Read bytes from file.
      FileStream fsIn = File.OpenRead(@".\characters.bin");
      BinaryReader br = new BinaryReader(fsIn);

      const int count = 10;            // Number of bytes to read at a time. 
      byte[] bytesRead = new byte[10]; // Buffer (byte array).
      int read;                        // Number of bytes actually read. 
      string str2 = String.Empty;      // Decoded string.

      // Try using Encoding object for all operations.
      do { 
         read = br.Read(bytesRead, 0, count);
         str2 += enc.GetString(bytesRead, 0, read); 
      } while (read == count);
      br.Close();
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...");
      CompareForEquality(str1, str2);
      Console.WriteLine();

      // Use Decoder for all operations.
      fsIn = File.OpenRead(@".\characters.bin");
      br = new BinaryReader(fsIn);
      Decoder decoder = enc.GetDecoder();
      char[] chars = new char[50];
      int index = 0;                   // Next character to write in array.
      int written = 0;                 // Number of chars written to array.
      do { 
         read = br.Read(bytesRead, 0, count);
         if (index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length) 
            Array.Resize(ref chars, chars.Length + 50);

         written = decoder.GetChars(bytesRead, 0, read, chars, index);
         index += written;                          
      } while (read == count);
      br.Close();            
      // Instantiate a string with the decoded characters.
      string str3 = new String(chars, 0, index); 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...");
      CompareForEquality(str1, str3); 
   }

   private static void CompareForEquality(string original, string decoded)
   {
      bool result = original.Equals(decoded);
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal));
      if (! result) {
         Console.WriteLine("Code points in original string:");
         foreach (var ch in original)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();

         Console.WriteLine("Code points in decoded string:");
         foreach (var ch in decoded)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    Created original string...
//    
//    Decoded string using UnicodeEncoding.GetString()...
//    original = decoded: False
//    Code points in original string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    Code points in decoded string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    
//    Decoded string using UnicodeEncoding.Decoder.GetString()...
//    original = decoded: True
```

```vb
Imports System.IO
Imports System.Text

Module Example
   Public Sub Main()
      ' Use default replacement fallback for invalid encoding.
      Dim enc As New UnicodeEncoding(True, False, False)

      ' Define a string with various Unicode characters.
      Dim str1 As String = String.Format("AB YZ 19 {0}{1} {2}", 
                                         ChrW(&hD800), ChrW(&hDC05), ChrW(&h00e4))
      str1 += String.Format("Unicode characters. {0} {1} s {2}{3}", 
                            ChrW(&h00a9), ChrW(&h010C), ChrW(&h0062), ChrW(&h0308))
      Console.WriteLine("Created original string...")
      Console.WriteLine()

      ' Convert string to byte array.                     
      Dim bytes() As Byte = enc.GetBytes(str1)

      Dim fs As FileStream = File.Create(".\characters.bin")
      Dim bw As New BinaryWriter(fs)
      bw.Write(bytes)
      bw.Close()

      ' Read bytes from file.
      Dim fsIn As FileStream = File.OpenRead(".\characters.bin")
      Dim br As New BinaryReader(fsIn)

      Const count As Integer = 10      ' Number of bytes to read at a time. 
      Dim bytesRead(9) As Byte         ' Buffer (byte array).
      Dim read As Integer              ' Number of bytes actually read. 
      Dim str2 As String = ""          ' Decoded string.

      ' Try using Encoding object for all operations.
      Do 
         read = br.Read(bytesRead, 0, count)
         str2 += enc.GetString(bytesRead, 0, read) 
      Loop While read = count
      br.Close()
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...")
      CompareForEquality(str1, str2)
      Console.WriteLine()

      ' Use Decoder for all operations.
      fsIn = File.OpenRead(".\characters.bin")
      br = New BinaryReader(fsIn)
      Dim decoder As Decoder = enc.GetDecoder()
      Dim chars(50) As Char
      Dim index As Integer = 0         ' Next character to write in array.
      Dim written As Integer = 0       ' Number of chars written to array.
      Do 
         read = br.Read(bytesRead, 0, count)
         If index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length Then 
            Array.Resize(chars, chars.Length + 50)
         End If   
         written = decoder.GetChars(bytesRead, 0, read, chars, index)
         index += written                          
      Loop While read = count
      br.Close()            
      ' Instantiate a string with the decoded characters.
      Dim str3 As New String(chars, 0, index) 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...")
      CompareForEquality(str1, str3) 
   End Sub

   Private Sub CompareForEquality(original As String, decoded As String)
      Dim result As Boolean = original.Equals(decoded)
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal))
      If Not result Then
         Console.WriteLine("Code points in original string:")
         For Each ch In original
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()

         Console.WriteLine("Code points in decoded string:")
         For Each ch In decoded
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
' The example displays the following output:
'    Created original string...
'    
'    Decoded string using UnicodeEncoding.GetString()...
'    original = decoded: False
'    Code points in original string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    Code points in decoded string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    
'    Decoded string using UnicodeEncoding.Decoder.GetString()...
'    original = decoded: True
```

## <a name="choosing-a-fallback-strategy"></a><span data-ttu-id="299ef-242">Scelta di una strategia di fallback</span><span class="sxs-lookup"><span data-stu-id="299ef-242">Choosing a fallback strategy</span></span>

<span data-ttu-id="299ef-243">Quando un metodo tenta di codificare o decodificare un carattere, ma non esiste alcun mapping, deve implementare una strategia di fallback che determina come gestire il mapping non riuscito.</span><span class="sxs-lookup"><span data-stu-id="299ef-243">When a method tries to encode or decode a character but no mapping exists, it must implement a fallback strategy that determines how the failed mapping should be handled.</span></span> <span data-ttu-id="299ef-244">Esistono tre tipi di strategie di fallback:</span><span class="sxs-lookup"><span data-stu-id="299ef-244">There are three types of fallback strategies:</span></span> 

* <span data-ttu-id="299ef-245">Fallback con mapping più appropriato</span><span class="sxs-lookup"><span data-stu-id="299ef-245">Best-fit fallback</span></span>

* <span data-ttu-id="299ef-246">Fallback di sostituzione</span><span class="sxs-lookup"><span data-stu-id="299ef-246">Replacement fallback</span></span>

* <span data-ttu-id="299ef-247">Fallback di eccezione</span><span class="sxs-lookup"><span data-stu-id="299ef-247">Exception fallback</span></span>

> [!IMPORTANT]
> <span data-ttu-id="299ef-248">I problemi più comuni nelle operazioni di codifica si verificano quando non è possibile eseguire il mapping di un carattere Unicode a una particolare codifica della tabella codici.</span><span class="sxs-lookup"><span data-stu-id="299ef-248">The most common problems in encoding operations occur when a Unicode character cannot be mapped to a particular code page encoding.</span></span> <span data-ttu-id="299ef-249">I problemi più comuni nelle operazioni di decodifica si verificano quando sequenze di byte non valide non possono essere convertite in caratteri Unicode validi.</span><span class="sxs-lookup"><span data-stu-id="299ef-249">The most common problems in decoding operations occur when invalid byte sequences cannot be translated into valid Unicode characters.</span></span> <span data-ttu-id="299ef-250">Per questi motivi, è opportuno conoscere la strategia di fallback usata da un oggetto di codifica specifico.</span><span class="sxs-lookup"><span data-stu-id="299ef-250">For these reasons, you should know which fallback strategy a particular encoding object uses.</span></span> <span data-ttu-id="299ef-251">Quando è possibile, è consigliabile specificare la strategia di fallback usata da un oggetto di codifica quando si crea un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="299ef-251">Whenever possible, you should specify the fallback strategy used by an encoding object when you instantiate the object.</span></span>
 
### <a name="best-fit-fallback"></a><span data-ttu-id="299ef-252">Fallback con mapping più appropriato</span><span class="sxs-lookup"><span data-stu-id="299ef-252">Best-fit fallback</span></span>

<span data-ttu-id="299ef-253">Quando un carattere non ha una corrispondenza esatta nella codifica di destinazione, il codificatore può provare a eseguirne il mapping a un carattere simile.</span><span class="sxs-lookup"><span data-stu-id="299ef-253">When a character does not have an exact match in the target encoding, the encoder can try to map it to a similar character.</span></span> <span data-ttu-id="299ef-254">Il fallback con mapping più appropriato è principalmente un problema di codifica più che di decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-254">(Best-fit fallback is mostly an encoding rather than a decoding issue.</span></span> <span data-ttu-id="299ef-255">Esistono pochissime tabelle codici contenenti caratteri di cui non è possibile eseguire correttamente il mapping a Unicode. Il fallback con mapping più appropriato è quello predefinito per le codifiche della tabella codici e Double Byte Character Set recuperate dagli overload [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) e [Encoding.GetEncoding(String)](xref:System.Text.Encoding.GetEncoding(System.String)).</span><span class="sxs-lookup"><span data-stu-id="299ef-255">There are very few code pages that contain characters that cannot be successfully mapped to Unicode.) Best-fit fallback is the default for code page and double-byte character set encodings that are retrieved by the [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) and [Encoding.GetEncoding(String)](xref:System.Text.Encoding.GetEncoding(System.String)) overloads.</span></span>

> [!NOTE]
> <span data-ttu-id="299ef-256">In teoria, le classi di codifica Unicode in .NET ([UTF8Encoding](xref:System.Text.UTF8Encoding), [UnicodeEncoding](xref:System.Text.UnicodeEncoding) e [UTF32Encoding](xref:System.Text.UTF32Encoding)) supportano ogni carattere di ogni set di caratteri e quindi possono essere usate per eliminare i problemi di fallback con mapping più appropriato.</span><span class="sxs-lookup"><span data-stu-id="299ef-256">In theory, the Unicode encoding classes provided in .NET ([UTF8Encoding](xref:System.Text.UTF8Encoding), [UnicodeEncoding](xref:System.Text.UnicodeEncoding), and [UTF32Encoding](xref:System.Text.UTF32Encoding)) support every character in every character set, so they can be used to eliminate best-fit fallback issues.</span></span> 
 

<span data-ttu-id="299ef-257">Le strategie di fallback con mapping più appropriato sono diverse a seconda delle tabelle codici e non sono documentate in dettaglio.</span><span class="sxs-lookup"><span data-stu-id="299ef-257">Best-fit strategies vary for different code pages, and they are not documented in detail.</span></span> <span data-ttu-id="299ef-258">Ad esempio, per alcune tabelle codici, dei caratteri latini a larghezza intera viene eseguito il mapping ai caratteri latini a metà larghezza più comuni.</span><span class="sxs-lookup"><span data-stu-id="299ef-258">For example, for some code pages, full-width Latin characters map to the more common half-width Latin characters.</span></span> <span data-ttu-id="299ef-259">Per altre tabelle codici, questo mapping non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="299ef-259">For other code pages, this mapping is not made.</span></span> <span data-ttu-id="299ef-260">Anche se si adotta una strategia aggressiva basata sul mapping più appropriato, per alcuni caratteri in alcune codifiche non è concepibile un mapping appropriato.</span><span class="sxs-lookup"><span data-stu-id="299ef-260">Even under an aggressive best-fit strategy, there is no imaginable fit for some characters in some encodings.</span></span> <span data-ttu-id="299ef-261">Ad esempio, per un ideogramma cinese non esistono mapping ragionevoli alla tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="299ef-261">For example, a Chinese ideograph has no reasonable mapping to code page 1252.</span></span> <span data-ttu-id="299ef-262">In questo caso, viene usata una stringa di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="299ef-262">In this case, a replacement string is used.</span></span> <span data-ttu-id="299ef-263">Per impostazione predefinita, questa stringa è semplicemente un punto interrogativo (QUESTION MARK, U+003F).</span><span class="sxs-lookup"><span data-stu-id="299ef-263">By default, this string is just a single QUESTION MARK (U+003F).</span></span>

<span data-ttu-id="299ef-264">L'esempio seguente usa la tabella codici 1252 (la tabella codici di Windows per le lingue dell'Europa occidentale) per illustrare il mapping più appropriato e i relativi svantaggi.</span><span class="sxs-lookup"><span data-stu-id="299ef-264">The following example uses code page 1252 (the Windows code page for Western European languages) to illustrate best-fit mapping and its drawbacks.</span></span> <span data-ttu-id="299ef-265">Viene usato il metodo [Encoding.GetEncoding(Int32](xref:System.Text.Encoding.GetEncoding(System.Int32)) per recuperare un oggetto di codifica per la tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="299ef-265">The [Encoding.GetEncoding(Int32](xref:System.Text.Encoding.GetEncoding(System.Int32)) method is used to retrieve an encoding object for code page 1252.</span></span> <span data-ttu-id="299ef-266">Per impostazione predefinita, usa il mapping più appropriato per i caratteri Unicode che non supporta.</span><span class="sxs-lookup"><span data-stu-id="299ef-266">By default, it uses a best-fit mapping for Unicode characters that it does not support.</span></span> <span data-ttu-id="299ef-267">L'esempio crea un'istanza di una stringa che contiene tre caratteri non ASCII, CIRCLED LATIN CAPITAL LETTER S (U+24C8), SUPERSCRIPT FIVE (U+2075) e INFINITY (U+221E), separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="299ef-267">The example instantiates a string that contains three non-ASCII characters - CIRCLED LATIN CAPITAL LETTER S (U+24C8), SUPERSCRIPT FIVE (U+2075), and INFINITY (U+221E) - separated by spaces.</span></span> <span data-ttu-id="299ef-268">Come mostra l'output del seguente esempio, quando la stringa viene codificata, i tre caratteri originali diversi dallo spazio vengono sostituiti da QUESTION MARK (U+003F), DIGIT FIVE (U+0035) e DIGIT EIGHT (U+0038).</span><span class="sxs-lookup"><span data-stu-id="299ef-268">As the output from the example shows, when the string is encoded, the three original non-space characters are replaced by QUESTION MARK (U+003F), DIGIT FIVE (U+0035), and DIGIT EIGHT (U+0038).</span></span> <span data-ttu-id="299ef-269">DIGIT EIGHT è una sostituzione del tutto inadeguata per il carattere INFINITY non supportato e QUESTION MARK indica che non è disponibile alcun mapping per il carattere originale.</span><span class="sxs-lookup"><span data-stu-id="299ef-269">DIGIT EIGHT is a particularly poor replacement for the unsupported INFINITY character, and QUESTION MARK indicates that no mapping was available for the original character.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Get an encoding for code page 1252 (Western Europe character set).
      Encoding cp1252 = Encoding.GetEncoding(1252);

      // Define and display a string.
      string str = "\u24c8 \u2075 \u221e";
      Console.WriteLine("Original string: " + str);
      Console.Write("Code points in string: ");
      foreach (var ch in str)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");   

      // Encode a Unicode string.
      Byte[] bytes = cp1252.GetBytes(str);
      Console.Write("Encoded bytes: ");
      foreach (byte byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the string.
      string str2 = cp1252.GetString(bytes);
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2));
      if (! str.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
      }
   }
}
// The example displays the following output:
//       Original string: Ⓢ ⁵ ∞
//       Code points in string: 24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 35 20 38
//       
//       String round-tripped: False
//       ? 5 8
//       003F 0020 0035 0020 0038
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      ' Get an encoding for code page 1252 (Western Europe character set).
      Dim cp1252 As Encoding = Encoding.GetEncoding(1252)

      ' Define and display a string.
      Dim str As String = String.Format("{0} {1} {2}", ChrW(&h24c8), ChrW(&H2075), ChrW(&h221E))
      Console.WriteLine("Original string: " + str)
      Console.Write("Code points in string: ")
      For Each ch In str
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next
      Console.WriteLine()   
      Console.WriteLine()

      ' Encode a Unicode string.
      Dim bytes() As Byte = cp1252.GetBytes(str)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the string.
      Dim str2 As String = cp1252.GetString(bytes)
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2))
      If Not str.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Original string: Ⓢ ⁵ ∞
'       Code points in string: 24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 35 20 38
'       
'       String round-tripped: False
'       ? 5 8
'       003F 0020 0035 0020 0038
```

<span data-ttu-id="299ef-270">Il mapping più appropriato è il comportamento predefinito per un oggetto [Encoding](xref:System.Text.Encoding) che codifica i dati Unicode come dati della tabella codici. Esistono applicazioni legacy che si basano su questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="299ef-270">Best-fit mapping is the default behavior for an [Encoding](xref:System.Text.Encoding) object that encodes Unicode data into code page data, and there are legacy applications that rely on this behavior.</span></span> <span data-ttu-id="299ef-271">Tuttavia, per motivi di sicurezza, per la maggior parte delle nuove applicazioni si dovrebbe evitare il comportamento basato sul mapping più appropriato.</span><span class="sxs-lookup"><span data-stu-id="299ef-271">However, most new applications should avoid best-fit behavior for security reasons.</span></span> <span data-ttu-id="299ef-272">Ad esempio, le applicazioni non dovrebbero inserire un nome di dominio tramite una codifica con mapping più appropriato.</span><span class="sxs-lookup"><span data-stu-id="299ef-272">For example, applications should not put a domain name through a best-fit encoding.</span></span>

> [!Note]
> <span data-ttu-id="299ef-273">Si può anche implementare un mapping basato sul fallback più appropriato personalizzato per una codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-273">You can also implement a custom best-fit fallback mapping for an encoding.</span></span> <span data-ttu-id="299ef-274">Per altre informazioni, vedere la sezione [Implementazione di una strategia di fallback personalizzata](#implementing-a-custom-fallback-strategy).</span><span class="sxs-lookup"><span data-stu-id="299ef-274">For more information, see the [Implementing a custom fallback strategy](#implementing-a-custom-fallback-strategy) section.</span></span>
 
<span data-ttu-id="299ef-275">Se il fallback con mapping più appropriato è la scelta predefinita per un oggetto di codifica, è possibile scegliere un'altra strategia di fallback quando si recupera un oggetto [Encoding](xref:System.Text.Encoding) chiamando l'overload [Encoding.GetEncoding(Int32, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)) o [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)).</span><span class="sxs-lookup"><span data-stu-id="299ef-275">If best-fit fallback is the default for an encoding object, you can choose another fallback strategy when you retrieve an [Encoding](xref:System.Text.Encoding) object by calling the [Encoding.GetEncoding(Int32, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)) or [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) overload.</span></span> <span data-ttu-id="299ef-276">La sezione seguente include un esempio che sostituisce con un asterisco (\*) ogni carattere di cui non è possibile eseguire il mapping alla tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="299ef-276">The following section includes an example that replaces each character that cannot be mapped to code page 1252 with an asterisk (\*).</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

### <a name="replacement-fallback"></a><span data-ttu-id="299ef-277">Fallback di sostituzione</span><span class="sxs-lookup"><span data-stu-id="299ef-277">Replacement fallback</span></span>

<span data-ttu-id="299ef-278">Quando un carattere non ha una corrispondenza esatta nello schema di destinazione e non esiste un carattere appropriato a cui eseguirne il mapping, l'applicazione può specificare una carattere o una stringa di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="299ef-278">When a character does not have an exact match in the target scheme, but there is no appropriate character that it can be mapped to, the application can specify a replacement character or string.</span></span> <span data-ttu-id="299ef-279">È il comportamento predefinito del decodificatore Unicode, che sostituisce con REPLACEMENT_CHARACTER (U+FFFD) le sequenze a due byte che non può decodificare.</span><span class="sxs-lookup"><span data-stu-id="299ef-279">This is the default behavior for the Unicode decoder, which replaces any two-byte sequence that it cannot decode with REPLACEMENT_CHARACTER (U+FFFD).</span></span> <span data-ttu-id="299ef-280">È anche il comportamento predefinito della classe [ASCIIEncoding](xref:System.Text.ASCIIEncoding), che sostituisce ogni carattere che non può codificare o decodificare con un punto interrogativo.</span><span class="sxs-lookup"><span data-stu-id="299ef-280">It is also the default behavior of the [ASCIIEncoding](xref:System.Text.ASCIIEncoding) class, which replaces each character that it cannot encode or decode with a question mark.</span></span> <span data-ttu-id="299ef-281">Il seguente esempio illustra la sostituzione dei caratteri della stringa Unicode dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="299ef-281">The following example illustrates character replacement for the Unicode string from the previous example.</span></span> <span data-ttu-id="299ef-282">Come mostra l'output, ogni carattere che non può essere decodificato con un byte ASCII viene sostituito da 0x3F, ovvero dal codice ASCII per il punto interrogativo.</span><span class="sxs-lookup"><span data-stu-id="299ef-282">As the output shows, each character that cannot be decoded into an ASCII byte value is replaced by 0x3F, which is the ASCII code for a question mark.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.ASCII;

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 3F 20 3F
//       
//       Round-trip: False
//       ? ? ?
//       003F 0020 003F 0020 003F
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.Ascii

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 3F 20 3F
'       
'       Round-trip: False
'       ? ? ?
'       003F 0020 003F 0020 003F
```

<span data-ttu-id="299ef-283">.NET include le classi [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) e [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback), che usano una stringa sostitutiva se non è possibile eseguire il mapping esatto di un carattere in un'operazione di codifica o decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-283">.NET includes the [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) and [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) classes, which substitute a replacement string if a character does not map exactly in an encoding or decoding operation.</span></span> <span data-ttu-id="299ef-284">Per impostazione predefinita, questa stringa di sostituzione è un punto interrogativo, ma è possibile chiamare un overload del costruttore di classe per scegliere un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="299ef-284">By default, this replacement string is a question mark, but you can call a class constructor overload to choose a different string.</span></span> <span data-ttu-id="299ef-285">In genere, la stringa di sostituzione è costituita da un solo carattere, anche se questo non è un requisito.</span><span class="sxs-lookup"><span data-stu-id="299ef-285">Typically, the replacement string is a single character, although this is not a requirement.</span></span> <span data-ttu-id="299ef-286">L'esempio seguente modifica il comportamento del codificatore della tabella codici 1252 creando un'istanza dell'oggetto [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) che usa un asterisco (\*) come stringa di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="299ef-286">The following example changes the behavior of the code page 1252 encoder by instantiating an [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) object that uses an asterisk (\*) as a replacement string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

> [!NOTE]
> <span data-ttu-id="299ef-287">Si può anche implementare una classe di sostituzione per una codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-287">You can also implement a replacement class for an encoding.</span></span> <span data-ttu-id="299ef-288">Per altre informazioni, vedere la sezione [Implementazione di una strategia di fallback personalizzata](#implementing-a-custom-fallback-strategy).</span><span class="sxs-lookup"><span data-stu-id="299ef-288">For more information, see the [Implementing a custom fallback strategy](#implementing-a-custom-fallback-strategy) section.</span></span>
 
<span data-ttu-id="299ef-289">Oltre a QUESTION MARK (U+003F), anche il carattere Unicode REPLACEMENT CHARACTER (U+FFFD) viene di solito usato come stringa di sostituzione, in particolare quando si decodificano sequenze di byte che non possono essere convertite in caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="299ef-289">In addition to QUESTION MARK (U+003F), the Unicode REPLACEMENT CHARACTER (U+FFFD) is commonly used as a replacement string, particularly when decoding byte sequences that cannot be successfully translated into Unicode characters.</span></span> <span data-ttu-id="299ef-290">Tuttavia è possibile scegliere qualsiasi stringa di sostituzione, che potrà contenere più caratteri.</span><span class="sxs-lookup"><span data-stu-id="299ef-290">However, you are free to choose any replacement string, and it can contain multiple characters.</span></span>

### <a name="exception-fallback"></a><span data-ttu-id="299ef-291">Fallback di eccezione</span><span class="sxs-lookup"><span data-stu-id="299ef-291">Exception fallback</span></span>

<span data-ttu-id="299ef-292">Invece di usare un fallback con mapping più appropriato o una stringa sostitutiva, un codificatore può generare un'eccezione [EncoderFallbackException](xref:System.Text.EncoderFallbackException) se non può codificare un set di caratteri, mentre un decodificatore può generare un'eccezione [DecoderFallbackException](xref:System.Text.DecoderFallbackException) se non può decodificare una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="299ef-292">Instead of providing a best-fit fallback or a replacement string, an encoder can throw an [EncoderFallbackException](xref:System.Text.EncoderFallbackException) if it is unable to encode a set of characters, and a decoder can throw a [DecoderFallbackException](xref:System.Text.DecoderFallbackException) if it is unable to decode a byte array.</span></span> <span data-ttu-id="299ef-293">Per generare un'eccezione nelle operazioni di codifica e decodifica, usare un oggetto [EncoderFallbackException](xref:System.Text.EncoderFallbackException) e [DecoderFallbackException](xref:System.Text.DecoderFallbackException) rispettivamente con il metodo [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)).</span><span class="sxs-lookup"><span data-stu-id="299ef-293">To throw an exception in encoding and decoding operations, you supply an [EncoderFallbackException](xref:System.Text.EncoderFallbackException) object and a [DecoderFallbackException](xref:System.Text.DecoderFallbackException) object, respectively, to the [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) method.</span></span> <span data-ttu-id="299ef-294">L'esempio seguente illustra il fallback di eccezione con la classe ASCIIEncoding.</span><span class="sxs-lookup"><span data-stu-id="299ef-294">The following example illustrates exception fallback with the ASCIIEncoding class.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", 
                                          new EncoderExceptionFallback(), 
                                          new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = {};
      try {
         bytes = enc.GetBytes(str1);
         Console.Write("Encoded bytes: ");
         foreach (var byt in bytes)
            Console.Write("{0:X2} ", byt);

         Console.WriteLine();
      }
      catch (EncoderFallbackException e) {
         Console.Write("Exception: ");
         if (e.IsUnknownSurrogate())
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index);
         else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index);
         return;
      }
      Console.WriteLine();

      // Decode the ASCII bytes.
      try {
         string str2 = enc.GetString(bytes);
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
         if (! str1.Equals(str2)) {
            Console.WriteLine(str2);
            foreach (var ch in str2)
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

            Console.WriteLine();
         } 
      }
      catch (DecoderFallbackException e) {
         Console.Write("Unable to decode byte(s) ");
         foreach (byte unknown in e.BytesUnknown)
            Console.Write("0x{0:X2} ");

         Console.WriteLine("at index {0}", e.Index);
      }
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Exception: Unable to encode 0x24C8 at index 0.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", 
                                                 New EncoderExceptionFallback(), 
                                                 New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = {}
      Try
         bytes = enc.GetBytes(str1)
         Console.Write("Encoded bytes: ")
         For Each byt In bytes
            Console.Write("{0:X2} ", byt)
         Next
         Console.WriteLine()
      Catch e As EncoderFallbackException
         Console.Write("Exception: ")
         If e.IsUnknownSurrogate() Then
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index)
         Else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index)
         End If                              
         Exit Sub
      End Try
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Try
         Dim str2 As String = enc.GetString(bytes)
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
         If Not str1.Equals(str2) Then
            Console.WriteLine(str2)
            For Each ch In str2
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
            Next    
            Console.WriteLine()
         End If 
      Catch e As DecoderFallbackException
         Console.Write("Unable to decode byte(s) ")
         For Each unknown As Byte In e.BytesUnknown
            Console.Write("0x{0:X2} ")
         Next
         Console.WriteLine("at index {0}", e.Index)
      End Try
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Exception: Unable to encode 0x24C8 at index 0.
```

> [!NOTE]
> <span data-ttu-id="299ef-295">Si può anche implementare un gestore di eccezioni personalizzato per un'operazione di codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-295">You can also implement a custom exception handler for an encoding operation.</span></span> <span data-ttu-id="299ef-296">Per altre informazioni, vedere la sezione [Implementazione di una strategia di fallback personalizzata](#implementing-a-custom-fallback-strategy).</span><span class="sxs-lookup"><span data-stu-id="299ef-296">For more information, see the [Implementing a custom fallback strategy](#implementing-a-custom-fallback-strategy) section.</span></span>
 
<span data-ttu-id="299ef-297">Gli oggetti [EncoderFallbackException](xref:System.Text.EncoderFallbackException) e [DecoderFallbackException](xref:System.Text.DecoderFallbackException) contengono le informazioni seguenti sulla condizione che ha causato l'eccezione:</span><span class="sxs-lookup"><span data-stu-id="299ef-297">The [EncoderFallbackException](xref:System.Text.EncoderFallbackException) and [DecoderFallbackException](xref:System.Text.DecoderFallbackException) objects provide the following information about the condition that caused the exception:</span></span> 

* <span data-ttu-id="299ef-298">L'oggetto [EncoderFallbackException](xref:System.Text.EncoderFallbackException) include un metodo [IsUnknownSurrogate](xref:System.Text.EncoderFallbackException.IsUnknownSurrogate), indicante se il carattere o i caratteri che non possono essere codificati rappresentano una coppia di surrogati sconosciuti. In questo caso, il metodo restituisce `true`. Se invece rappresentano un singolo carattere sconosciuto, il metodo restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="299ef-298">The [EncoderFallbackException](xref:System.Text.EncoderFallbackException) object includes an [IsUnknownSurrogate](xref:System.Text.EncoderFallbackException.IsUnknownSurrogate) method, which indicates whether the character or characters that cannot be encoded represent an unknown surrogate pair (in which case, the method returns `true`) or an unknown single character (in which case, the method returns `false`).</span></span> <span data-ttu-id="299ef-299">I caratteri della coppia di surrogati sono recuperati dalle proprietà [EncoderFallbackException.CharUnknownHigh](xref:System.Text.EncoderFallbackException.CharUnknownHigh) e [EncoderFallbackException.CharUnknownLow](xref:System.Text.EncoderFallbackException.CharUnknownLow).</span><span class="sxs-lookup"><span data-stu-id="299ef-299">The characters in the surrogate pair are available from the [EncoderFallbackException.CharUnknownHigh](xref:System.Text.EncoderFallbackException.CharUnknownHigh) and [EncoderFallbackException.CharUnknownLow](xref:System.Text.EncoderFallbackException.CharUnknownLow) properties.</span></span> <span data-ttu-id="299ef-300">Il singolo carattere sconosciuto è invece recuperato dalla proprietà [EncoderFallbackException.CharUnknown](xref:System.Text.EncoderFallbackException.CharUnknown).</span><span class="sxs-lookup"><span data-stu-id="299ef-300">The unknown single character is available from the [EncoderFallbackException.CharUnknown](xref:System.Text.EncoderFallbackException.CharUnknown) property.</span></span> <span data-ttu-id="299ef-301">La proprietà [EncoderFallbackException.Index](xref:System.Text.EncoderFallbackException.Index) indica la posizione nella stringa in cui è stato trovato il primo carattere che non è stato possibile codificare.</span><span class="sxs-lookup"><span data-stu-id="299ef-301">The [EncoderFallbackException.Index](xref:System.Text.EncoderFallbackException.Index) property indicates the position in the string at which the first character that could not be encoded was found.</span></span>

* <span data-ttu-id="299ef-302">L'oggetto [DecoderFallbackException](xref:System.Text.DecoderFallbackException) include una proprietà [BytesUnknown](xref:System.Text.DecoderFallbackException.BytesUnknown) che restituisce una matrice di byte che non è possibile decodificare.</span><span class="sxs-lookup"><span data-stu-id="299ef-302">The [DecoderFallbackException](xref:System.Text.DecoderFallbackException) object includes a [BytesUnknown](xref:System.Text.DecoderFallbackException.BytesUnknown) property that returns an array of bytes that cannot be decoded.</span></span> <span data-ttu-id="299ef-303">La proprietà [DecoderFallbackException.Index](xref:System.Text.DecoderFallbackException.Index) indica la posizione iniziale dei byte sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="299ef-303">The [DecoderFallbackException.Index](xref:System.Text.DecoderFallbackException.Index) property indicates the starting position of the unknown bytes.</span></span>

<span data-ttu-id="299ef-304">Anche se gli oggetti [EncoderFallbackException](xref:System.Text.EncoderFallbackException) e [DecoderFallbackException](xref:System.Text.DecoderFallbackException) contengono informazioni diagnostiche adeguate sull'eccezione, non consentono tuttavia l'accesso al buffer di codifica o di decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-304">Although the [EncoderFallbackException](xref:System.Text.EncoderFallbackException) and [DecoderFallbackException](xref:System.Text.DecoderFallbackException) objects provide adequate diagnostic information about the exception, they do not provide access to the encoding or decoding buffer.</span></span> <span data-ttu-id="299ef-305">Quindi non consentono di sostituire o correggere i dati non validi nel metodo di codifica o di decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-305">Therefore, they do not allow invalid data to be replaced or corrected within the encoding or decoding method.</span></span>

## <a name="implementing-a-custom-fallback-strategy"></a><span data-ttu-id="299ef-306">Implementazione di una strategia di fallback personalizzata</span><span class="sxs-lookup"><span data-stu-id="299ef-306">Implementing a custom fallback strategy</span></span>

<span data-ttu-id="299ef-307">Oltre al mapping più appropriato che viene implementato internamente dalle tabelle codici, .NET include le classi seguenti per implementare una strategia di fallback:</span><span class="sxs-lookup"><span data-stu-id="299ef-307">In addition to the best-fit mapping that is implemented internally by code pages, .NET includes the following classes for implementing a fallback strategy:</span></span>

* <span data-ttu-id="299ef-308">Usare [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) e [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) per sostituire i caratteri nelle operazioni di codifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-308">Use [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) and [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) to replace characters in encoding operations.</span></span>

* <span data-ttu-id="299ef-309">Usare [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) e [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) per sostituire i caratteri nelle operazioni di decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-309">Use [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) and [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) to replace characters in decoding operations.</span></span>

* <span data-ttu-id="299ef-310">Usare [EncoderExceptionFallback](xref:System.Text.EncoderExceptionFallback) e [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) per generare un'eccezione [EncoderFallbackException](xref:System.Text.EncoderFallbackException) quando un carattere non può essere codificato.</span><span class="sxs-lookup"><span data-stu-id="299ef-310">Use [EncoderExceptionFallback](xref:System.Text.EncoderExceptionFallback) and [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) to throw an [EncoderFallbackException](xref:System.Text.EncoderFallbackException) when a character cannot be encoded.</span></span>

* <span data-ttu-id="299ef-311">Usare [DecoderExceptionFallback](xref:System.Text.DecoderExceptionFallback) e [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) per generare un'eccezione [DecoderFallbackException](xref:System.Text.DecoderFallbackException) quando un carattere non può essere decodificato.</span><span class="sxs-lookup"><span data-stu-id="299ef-311">Use [DecoderExceptionFallback](xref:System.Text.DecoderExceptionFallback) and [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) to throw a [DecoderFallbackException](xref:System.Text.DecoderFallbackException) when a character cannot be decoded.</span></span>

<span data-ttu-id="299ef-312">Inoltre, è possibile implementare una soluzione personalizzata che usa il fallback con mapping più appropriato, il fallback di sostituzione o il fallback di eccezione, attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="299ef-312">In addition, you can implement a custom solution that uses best-fit fallback, replacement fallback, or exception fallback, by following these steps:</span></span> 

1. <span data-ttu-id="299ef-313">Derivare una classe da [EncoderFallback](xref:System.Text.EncoderFallback) per le operazioni di codifica e da [DecoderFallback](xref:System.Text.DecoderFallback) per le operazioni di decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-313">Derive a class from [EncoderFallback](xref:System.Text.EncoderFallback) for encoding operations, and from [DecoderFallback](xref:System.Text.DecoderFallback) for decoding operations.</span></span>

2. <span data-ttu-id="299ef-314">Derivare una classe da [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) per le operazioni di codifica e da [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) per le operazioni di decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-314">Derive a class from [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) for encoding operations, and from [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) for decoding operations.</span></span>

3. <span data-ttu-id="299ef-315">In caso di fallback di eccezione, se le classi [EncoderFallbackException](xref:System.Text.EncoderFallbackException) e [DecoderFallbackException](xref:System.Text.DecoderFallbackException) predefinite non sono soddisfacenti, derivare una classe da un oggetto eccezione, ad esempio [Exception](xref:System.Exception) o [ArgumentException](xref:System.ArgumentException).</span><span class="sxs-lookup"><span data-stu-id="299ef-315">For exception fallback, if the predefined [EncoderFallbackException](xref:System.Text.EncoderFallbackException) and [DecoderFallbackException](xref:System.Text.DecoderFallbackException) classes do not meet your needs, derive a class from an exception object such as [Exception](xref:System.Exception) or [ArgumentException](xref:System.ArgumentException).</span></span>

### <a name="deriving-from-encoderfallback-or-decoderfallback"></a><span data-ttu-id="299ef-316">Derivazione da EncoderFallback o DecoderFallback</span><span class="sxs-lookup"><span data-stu-id="299ef-316">Deriving from EncoderFallback or DecoderFallback</span></span>

<span data-ttu-id="299ef-317">Per implementare una soluzione di fallback personalizzata, è necessario creare una classe che eredita da [EncoderFallback](xref:System.Text.EncoderFallback) per le operazioni di codifica e da [DecoderFallback](xref:System.Text.DecoderFallback) per le operazioni di decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-317">To implement a custom fallback solution, you must create a class that inherits from [EncoderFallback](xref:System.Text.EncoderFallback) for encoding operations, and from [DecoderFallback](xref:System.Text.DecoderFallback) for decoding operations.</span></span> <span data-ttu-id="299ef-318">Le istanze di queste classi vengono passate al metodo [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) e fungono da intermediario tra la classe Encoding e l'implementazione del fallback.</span><span class="sxs-lookup"><span data-stu-id="299ef-318">Instances of these classes are passed to the [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) method and serve as the intermediary between the encoding class and the fallback implementation.</span></span>

<span data-ttu-id="299ef-319">Quando si crea una soluzione di fallback personalizzata per un codificatore o un decodificatore, è necessario implementare i membri seguenti:</span><span class="sxs-lookup"><span data-stu-id="299ef-319">When you create a custom fallback solution for an encoder or decoder, you must implement the following members:</span></span>

* <span data-ttu-id="299ef-320">La proprietà [EncoderFallback.MaxCharCount](xref:System.Text.EncoderFallback.MaxCharCount) o [DecoderFallback.MaxCharCount](xref:System.Text.DecoderFallback.MaxCharCount) che restituisce il numero massimo possibile di caratteri che il fallback con mapping più appropriato, di sostituzione o di eccezione può restituire per sostituire un singolo carattere.</span><span class="sxs-lookup"><span data-stu-id="299ef-320">The [EncoderFallback.MaxCharCount](xref:System.Text.EncoderFallback.MaxCharCount) or [DecoderFallback.MaxCharCount](xref:System.Text.DecoderFallback.MaxCharCount) property, which returns the maximum possible number of characters that the best-fit, replacement, or exception fallback can return to replace a single character.</span></span> <span data-ttu-id="299ef-321">Per un fallback di eccezione personalizzata, il valore è zero.</span><span class="sxs-lookup"><span data-stu-id="299ef-321">For a custom exception fallback, its value is zero.</span></span> 

* <span data-ttu-id="299ef-322">Il metodo [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) o [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer), che restituisce l'implementazione di [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) o [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) personalizzata.</span><span class="sxs-lookup"><span data-stu-id="299ef-322">The [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) or [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer) method, which returns your custom [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) or [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) implementation.</span></span> <span data-ttu-id="299ef-323">Il metodo viene chiamato dal codificatore quando rileva il primo carattere che non può codificare correttamente oppure dal decodificatore quando rileva il primo byte che non può decodificare correttamente.</span><span class="sxs-lookup"><span data-stu-id="299ef-323">The method is called by the encoder when it encounters the first character that it is unable to successfully encode, or by the decoder when it encounters the first byte that it is unable to successfully decode.</span></span>

### <a name="deriving-from-encoderfallbackbuffer-or-decoderfallbackbuffer"></a><span data-ttu-id="299ef-324">Derivazione da EncoderFallbackBuffer o DecoderFallbackBuffer</span><span class="sxs-lookup"><span data-stu-id="299ef-324">Deriving from EncoderFallbackBuffer or DecoderFallbackBuffer</span></span>

<span data-ttu-id="299ef-325">Per implementare una soluzione di fallback personalizzata, è necessario creare anche una classe che eredita da [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) per le operazioni di codifica e da [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) per le operazioni di decodifica.</span><span class="sxs-lookup"><span data-stu-id="299ef-325">To implement a custom fallback solution, you must also create a class that inherits from [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) for encoding operations, and from [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) for decoding operations.</span></span> <span data-ttu-id="299ef-326">Le istanze di queste classi vengono restituite dal metodo `CreateFallbackBuffer` delle classi [EncoderFallback](xref:System.Text.EncoderFallback) e [DecoderFallback](xref:System.Text.DecoderFallback).</span><span class="sxs-lookup"><span data-stu-id="299ef-326">Instances of these classes are returned by the `CreateFallbackBuffer` method of the [EncoderFallback](xref:System.Text.EncoderFallback) and [DecoderFallback](xref:System.Text.DecoderFallback) classes.</span></span> <span data-ttu-id="299ef-327">Il metodo [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) viene chiamato dal codificatore quando rileva il primo carattere che non può codificare, mentre il metodo [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer) viene chiamato dal decodificatore quando rileva uno o più byte che non può decodificare.</span><span class="sxs-lookup"><span data-stu-id="299ef-327">The [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) method is called by the encoder when it encounters the first character that it is not able to encode, and the [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer) method is called by the decoder when it encounters one or more bytes that it is not able to decode.</span></span> <span data-ttu-id="299ef-328">Le classi [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) e [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) consentono l'implementazione del fallback.</span><span class="sxs-lookup"><span data-stu-id="299ef-328">The [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) and [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) classes provide the fallback implementation.</span></span> <span data-ttu-id="299ef-329">Ogni istanza rappresenta un buffer contenente i caratteri di fallback che sostituiranno il carattere che non può essere codificato o la sequenza di byte che non può essere decodificata.</span><span class="sxs-lookup"><span data-stu-id="299ef-329">Each instance represents a buffer that contains the fallback characters that will replace the character that cannot be encoded or the byte sequence that cannot be decoded.</span></span>

<span data-ttu-id="299ef-330">Quando si crea una soluzione di fallback personalizzata per un codificatore o un decodificatore, è necessario implementare i membri seguenti:</span><span class="sxs-lookup"><span data-stu-id="299ef-330">When you create a custom fallback solution for an encoder or decoder, you must implement the following members:</span></span>

* <span data-ttu-id="299ef-331">Il metodo [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.%23ctor) o [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)).</span><span class="sxs-lookup"><span data-stu-id="299ef-331">The [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.%23ctor) or [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)) method.</span></span> <span data-ttu-id="299ef-332">Il metodo [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.Fallback(System.Char,System.Char,System.Int32)) viene chiamato dal codificatore per comunicare al buffer di fallback informazioni sul carattere che non può codificare.</span><span class="sxs-lookup"><span data-stu-id="299ef-332">[EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.Fallback(System.Char,System.Char,System.Int32)) is called by the encoder to provide the fallback buffer with information about the character that it cannot encode.</span></span> <span data-ttu-id="299ef-333">Poiché il carattere da codificare può essere una coppia di surrogati, questo metodo viene sottoposto a overload.</span><span class="sxs-lookup"><span data-stu-id="299ef-333">Because the character to be encoded may be a surrogate pair, this method is overloaded.</span></span> <span data-ttu-id="299ef-334">A un overload vengono passati il carattere da codificare e l'indice nella stringa.</span><span class="sxs-lookup"><span data-stu-id="299ef-334">One overload is passed the character to be encoded and its index in the string.</span></span> <span data-ttu-id="299ef-335">Al secondo overload vengono passati il surrogato alto e quello basso insieme all'indice nella stringa.</span><span class="sxs-lookup"><span data-stu-id="299ef-335">The second overload is passed the high and low surrogate along with its index in the string.</span></span> <span data-ttu-id="299ef-336">Il metodo [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)) viene chiamato dal decodificatore per comunicare al buffer di fallback informazioni sul carattere che non può decodificare.</span><span class="sxs-lookup"><span data-stu-id="299ef-336">The [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)) method is called by the decoder to provide the fallback buffer with information about the bytes that it cannot decode.</span></span> <span data-ttu-id="299ef-337">A questo metodo viene passata una matrice di byte che non può decodificare, insieme all'indice del primo byte.</span><span class="sxs-lookup"><span data-stu-id="299ef-337">This method is passed an array of bytes that it cannot decode, along with the index of the first byte.</span></span> <span data-ttu-id="299ef-338">Il metodo di fallback dovrebbe restituire `true` se il buffer di fallback può fornire uno o più caratteri di sostituzione o con mapping più appropriato. In caso contrario, dovrebbe restituire `false`.</span><span class="sxs-lookup"><span data-stu-id="299ef-338">The fallback method should return `true` if the fallback buffer can supply a best-fit or replacement character or characters; otherwise, it should return `false`.</span></span> <span data-ttu-id="299ef-339">Per un fallback di eccezione, il metodo di fallback dovrebbe generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="299ef-339">For an exception fallback, the fallback method should throw an exception.</span></span>

* <span data-ttu-id="299ef-340">Il metodo [EncoderFallbackBuffer.GetNextChar](xref:System.Text.EncoderFallbackBuffer.GetNextChar) o [DecoderFallbackBuffer.GetNextChar](xref:System.Text.DecoderFallbackBuffer.GetNextChar), che viene chiamato ripetutamente dal codificatore o dal decodificatore per ottenere il carattere successivo dal buffer di fallback.</span><span class="sxs-lookup"><span data-stu-id="299ef-340">The [EncoderFallbackBuffer.GetNextChar](xref:System.Text.EncoderFallbackBuffer.GetNextChar) or [DecoderFallbackBuffer.GetNextChar](xref:System.Text.DecoderFallbackBuffer.GetNextChar) method, which is called repeatedly by the encoder or decoder to get the next character from the fallback buffer.</span></span> <span data-ttu-id="299ef-341">Quando sono stati restituiti tutti i caratteri di fallback, il metodo dovrebbe restituire U+0000.</span><span class="sxs-lookup"><span data-stu-id="299ef-341">When all fallback characters have been returned, the method should return U+0000.</span></span> 

* <span data-ttu-id="299ef-342">La proprietà [EncoderFallbackBuffer.Remaining](xref:System.Text.EncoderFallbackBuffer.Remaining) o [DecoderFallbackBuffer.Remaining](xref:System.Text.DecoderFallbackBuffer.Remaining) che restituisce il numero di caratteri rimanenti nel buffer di fallback.</span><span class="sxs-lookup"><span data-stu-id="299ef-342">The [EncoderFallbackBuffer.Remaining](xref:System.Text.EncoderFallbackBuffer.Remaining) or [DecoderFallbackBuffer.Remaining](xref:System.Text.DecoderFallbackBuffer.Remaining) property, which returns the number of characters remaining in the fallback buffer.</span></span>

* <span data-ttu-id="299ef-343">Il metodo [EncoderFallbackBuffer.MovePrevious](xref:System.Text.EncoderFallbackBuffer.MovePrevious) o [DecoderFallbackBuffer.MovePrevious](xref:System.Text.DecoderFallbackBuffer.MovePrevious), che sposta la posizione corrente nel buffer di fallback al carattere precedente.</span><span class="sxs-lookup"><span data-stu-id="299ef-343">The [EncoderFallbackBuffer.MovePrevious](xref:System.Text.EncoderFallbackBuffer.MovePrevious) or [DecoderFallbackBuffer.MovePrevious](xref:System.Text.DecoderFallbackBuffer.MovePrevious) method, which moves the current position in the fallback buffer to the previous character.</span></span>

* <span data-ttu-id="299ef-344">Il metodo [EncoderFallbackBuffer.Reset](xref:System.Text.EncoderFallbackBuffer.Reset) o [DecoderFallbackBuffer.Reset](xref:System.Text.DecoderFallbackBuffer.Reset), che reinizializza il buffer di fallback.</span><span class="sxs-lookup"><span data-stu-id="299ef-344">The [EncoderFallbackBuffer.Reset](xref:System.Text.EncoderFallbackBuffer.Reset) or [DecoderFallbackBuffer.Reset](xref:System.Text.DecoderFallbackBuffer.Reset) method, which reinitializes the fallback buffer.</span></span>

<span data-ttu-id="299ef-345">Se l'implementazione del fallback è un fallback con mapping più appropriato o un fallback di sostituzione, le classi derivate da [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) e [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) gestiscono anche due campi di istanza privata, vale a dire il numero esatto di caratteri nel buffer e l'indice del carattere successivo nel buffer da restituire.</span><span class="sxs-lookup"><span data-stu-id="299ef-345">If the fallback implementation is a best-fit fallback or a replacement fallback, the classes derived from [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) and [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) also maintain two private instance fields: the exact number of characters in the buffer; and the index of the next character in the buffer to return.</span></span>

### <a name="an-encoderfallback-example"></a><span data-ttu-id="299ef-346">Esempio di EncoderFallback</span><span class="sxs-lookup"><span data-stu-id="299ef-346">An EncoderFallback example</span></span>

<span data-ttu-id="299ef-347">In un esempio precedente è stato usato il fallback di sostituzione per sostituire con un asterisco (\*) i caratteri Unicode non corrispondenti a caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="299ef-347">An earlier example used replacement fallback to replace Unicode characters that did not correspond to ASCII characters with an asterisk (\*).</span></span> <span data-ttu-id="299ef-348">L'esempio seguente usa un'implementazione del fallback con mapping più appropriato personalizzato invece di fornire un mapping migliore dei caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="299ef-348">The following example uses a custom best-fit fallback implementation instead to provide a better mapping of non-ASCII characters.</span></span>

<span data-ttu-id="299ef-349">Il codice seguente definisce una classe denominata `CustomMapper` derivata da [EncoderFallback](xref:System.Text.EncoderFallback) per gestire il mapping più appropriato di caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="299ef-349">The following code defines a class named `CustomMapper` that is derived from [EncoderFallback](xref:System.Text.EncoderFallback) to handle the best-fit mapping of non-ASCII characters.</span></span> <span data-ttu-id="299ef-350">Il metodo `CreateFallbackBuffer` restituisce un oggetto `CustomMapperFallbackBuffer`, che consente l'implementazione di [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer).</span><span class="sxs-lookup"><span data-stu-id="299ef-350">Its `CreateFallbackBuffer` method returns a `CustomMapperFallbackBuffer` object, which provides the [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) implementation.</span></span> <span data-ttu-id="299ef-351">La classe `CustomMapper` usa un oggetto [Dictionary&lt;TKey, TValue&gt;](xref:System.Collections.Generic.Dictionary%602) per archiviare i mapping di caratteri Unicode non supportati (valore chiave) e i relativi caratteri a 8 bit, che vengono archiviati in due byte consecutivi in un Integer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="299ef-351">The `CustomMapper` class uses a [Dictionary&lt;TKey, TValue&gt;](xref:System.Collections.Generic.Dictionary%602) object to store the mappings of unsupported Unicode characters (the key value) and their corresponding 8-bit characters (which are stored in two consecutive bytes in a 64-bit integer).</span></span> <span data-ttu-id="299ef-352">Per rendere questo mapping disponibile al buffer di fallback, l'istanza di `CustomMapper` viene passata come parametro al costruttore di classe `CustomMapperFallbackBuffer`.</span><span class="sxs-lookup"><span data-stu-id="299ef-352">To make this mapping available to the fallback buffer, the `CustomMapper` instance is passed as a parameter to the `CustomMapperFallbackBuffer` class constructor.</span></span> <span data-ttu-id="299ef-353">Poiché il mapping di più lungo è la stringa "INF" per il carattere Unicode U+221E, la proprietà `MaxCharCount` restituisce 3.</span><span class="sxs-lookup"><span data-stu-id="299ef-353">Because the longest mapping is the string "INF" for the Unicode character U+221E, the `MaxCharCount` property returns 3.</span></span> 

```csharp
public class CustomMapper : EncoderFallback
{
   public string DefaultString;
   internal Dictionary<ushort, ulong> mapping;

   public CustomMapper() : this("*")
   {   
   }

   public CustomMapper(string defaultString)
   {
      this.DefaultString = defaultString;

      // Create table of mappings
      mapping = new Dictionary<ushort, ulong>();
      mapping.Add(0x24C8, 0x53);
      mapping.Add(0x2075, 0x35);
      mapping.Add(0x221E, 0x49004E0046);
   }

   public override EncoderFallbackBuffer CreateFallbackBuffer()
   {
      return new CustomMapperFallbackBuffer(this);
   }

   public override int MaxCharCount
   {
      get { return 3; }
   } 
}
```

```vb
Public Class CustomMapper : Inherits EncoderFallback
   Public DefaultString As String
   Friend mapping As Dictionary(Of UShort, ULong)

   Public Sub New()
      Me.New("?")
   End Sub

   Public Sub New(ByVal defaultString As String)
      Me.DefaultString = defaultString

      ' Create table of mappings
      mapping = New Dictionary(Of UShort, ULong)
      mapping.Add(&H24C8, &H53)
      mapping.Add(&H2075, &H35)
      mapping.Add(&H221E, &H49004E0046)
   End Sub

   Public Overrides Function CreateFallbackBuffer() As System.Text.EncoderFallbackBuffer
      Return New CustomMapperFallbackBuffer(Me)
   End Function

   Public Overrides ReadOnly Property MaxCharCount As Integer
      Get
         Return 3
      End Get
   End Property
End Class
```

<span data-ttu-id="299ef-354">Il codice seguente definisce la classe `CustomMapperFallbackBuffer`, derivata da [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer).</span><span class="sxs-lookup"><span data-stu-id="299ef-354">The following code defines the `CustomMapperFallbackBuffer` class, which is derived from [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer).</span></span> <span data-ttu-id="299ef-355">Il dizionario contenente i mapping più appropriati e definito nell'istanza di `CustomMapper` è disponibile nel costruttore di classe.</span><span class="sxs-lookup"><span data-stu-id="299ef-355">The dictionary that contains best-fit mappings and that is defined in the `CustomMapper` instance is available from its class constructor.</span></span> <span data-ttu-id="299ef-356">Il metodo `Fallback` restituisce `true` se uno dei caratteri Unicode che il codificatore ASCII non può codificare è definito nel dizionario dei mapping. In caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="299ef-356">Its `Fallback` method returns `true` if any of the Unicode characters that the ASCII encoder cannot encode are defined in the mapping dictionary; otherwise, it returns `false`.</span></span> <span data-ttu-id="299ef-357">Per ogni fallback, la variabile privata `count` indica il numero di caratteri ancora da restituire e la variabile privata `index` indica la posizione nel buffer della stringa, `charsToReturn`, del carattere successivo da restituire.</span><span class="sxs-lookup"><span data-stu-id="299ef-357">For each fallback, the private `count` variable indicates the number of characters that remain to be returned, and the private `index` variable indicates the position in the string buffer, `charsToReturn`, of the next character to return.</span></span> 

```csharp
public class CustomMapperFallbackBuffer : EncoderFallbackBuffer
{
   int count = -1;                   // Number of characters to return
   int index = -1;                   // Index of character to return
   CustomMapper fb; 
   string charsToReturn; 

   public CustomMapperFallbackBuffer(CustomMapper fallback)
   {
      this.fb = fallback;
   }

   public override bool Fallback(char charUnknownHigh, char charUnknownLow, int index)
   {
      // Do not try to map surrogates to ASCII.
      return false;
   }

   public override bool Fallback(char charUnknown, int index)
   {
      // Return false if there are already characters to map.
      if (count >= 1) return false;

      // Determine number of characters to return.
      charsToReturn = String.Empty;

      ushort key = Convert.ToUInt16(charUnknown);
      if (fb.mapping.ContainsKey(key)) {
         byte[] bytes = BitConverter.GetBytes(fb.mapping[key]);
         int ctr = 0;
         foreach (var byt in bytes) {
            if (byt > 0) {
               ctr++;
               charsToReturn += (char) byt;
            }
         }
         count = ctr;
      }
      else {
         // Return default.
         charsToReturn = fb.DefaultString;
         count = 1;
      }
      this.index = charsToReturn.Length - 1;

      return true;
   }

   public override char GetNextChar()
   {
      // We'll return a character if possible, so subtract from the count of chars to return.
      count--;
      // If count is less than zero, we've returned all characters.
      if (count < 0) 
         return '\u0000';

      this.index--;
      return charsToReturn[this.index + 1];
   }

   public override bool MovePrevious()
   {
      // Original: if count >= -1 and pos >= 0
      if (count >= -1) {
         count++;
         return true;
      }
      else {
         return false;
      }
   }

   public override int Remaining 
   {
      get { return count < 0 ? 0 : count; }
   }

   public override void Reset()
   {
      count = -1;
      index = -1;
   }
}
```

```vb
Public Class CustomMapperFallbackBuffer : Inherits EncoderFallbackBuffer

   Dim count As Integer = -1        ' Number of characters to return
   Dim index As Integer = -1        ' Index of character to return
   Dim fb As CustomMapper
   Dim charsToReturn As String

   Public Sub New(ByVal fallback As CustomMapper)
      MyBase.New()
      Me.fb = fallback
   End Sub

   Public Overloads Overrides Function Fallback(ByVal charUnknownHigh As Char, ByVal charUnknownLow As Char, ByVal index As Integer) As Boolean
      ' Do not try to map surrogates to ASCII.
      Return False
   End Function

   Public Overloads Overrides Function Fallback(ByVal charUnknown As Char, ByVal index As Integer) As Boolean
      ' Return false if there are already characters to map.
      If count >= 1 Then Return False

      ' Determine number of characters to return.
      charsToReturn = String.Empty

      Dim key As UShort = Convert.ToUInt16(charUnknown)
      If fb.mapping.ContainsKey(key) Then
         Dim bytes() As Byte = BitConverter.GetBytes(fb.mapping.Item(key))
         Dim ctr As Integer
         For Each byt In bytes
            If byt > 0 Then
               ctr += 1
               charsToReturn += Chr(byt)
            End If
         Next
         count = ctr
      Else
         ' Return default.
         charsToReturn = fb.DefaultString
         count = 1
      End If
      Me.index = charsToReturn.Length - 1

      Return True
   End Function

   Public Overrides Function GetNextChar() As Char
      ' We'll return a character if possible, so subtract from the count of chars to return.
      count -= 1
      ' If count is less than zero, we've returned all characters.
      If count < 0 Then Return ChrW(0)

      Me.index -= 1
      Return charsToReturn(Me.index + 1)
   End Function

   Public Overrides Function MovePrevious() As Boolean
      ' Original: if count >= -1 and pos >= 0
      If count >= -1 Then
         count += 1
         Return True
      Else
         Return False
      End If
   End Function

   Public Overrides ReadOnly Property Remaining As Integer
      Get
         Return If(count < 0, 0, count)
      End Get
   End Property

   Public Overrides Sub Reset()
      count = -1
      index = -1
   End Sub
End Class
```

<span data-ttu-id="299ef-358">Il codice seguente crea poi un'istanza dell'oggetto `CustomMapper` e la passa al metodo [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)).</span><span class="sxs-lookup"><span data-stu-id="299ef-358">The following code then instantiates the `CustomMapper` object and passes an instance of it to the [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) method.</span></span> <span data-ttu-id="299ef-359">L'output indica che l'implementazione del fallback con mapping più appropriato gestisce correttamente i tre caratteri non ASCII nella stringa originale.</span><span class="sxs-lookup"><span data-stu-id="299ef-359">The output indicates that the best-fit fallback implementation successfully handles the three non-ASCII characters in the original string.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Text;

class Program
{
   static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", new CustomMapper(), new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      for (int ctr = 0; ctr <= str1.Length - 1; ctr++) {
         Console.Write("{0} ", Convert.ToUInt16(str1[ctr]).ToString("X4"));
         if (ctr == str1.Length - 1) 
            Console.WriteLine();
      }
      Console.WriteLine();

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);

      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      }
   }
}
```

```vb
Imports System.Text
Imports System.Collections.Generic

Module Module1

   Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", New CustomMapper(), New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&H24C8), ChrW(&H2075), ChrW(&H221E))
      Console.WriteLine(str1)
      For ctr As Integer = 0 To str1.Length - 1
         Console.Write("{0} ", Convert.ToUInt16(str1(ctr)).ToString("X4"))
         If ctr = str1.Length - 1 Then Console.WriteLine()
      Next
      Console.WriteLine()

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="299ef-360">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="299ef-360">See also</span></span>

[<span data-ttu-id="299ef-361">System.Text.Encoder</span><span class="sxs-lookup"><span data-stu-id="299ef-361">System.Text.Encoder</span></span>](xref:System.Text.Encoder)

[<span data-ttu-id="299ef-362">System.Text.EncoderFallback</span><span class="sxs-lookup"><span data-stu-id="299ef-362">System.Text.EncoderFallback</span></span>](xref:System.Text.EncoderFallback)

[<span data-ttu-id="299ef-363">System.Text.Decoder</span><span class="sxs-lookup"><span data-stu-id="299ef-363">System.Text.Decoder</span></span>](xref:System.Text.Decoder)

[<span data-ttu-id="299ef-364">System.Text.DecoderFallback</span><span class="sxs-lookup"><span data-stu-id="299ef-364">System.Text.DecoderFallback</span></span>](xref:System.Text.DecoderFallback)

[<span data-ttu-id="299ef-365">System.Text.Encoding</span><span class="sxs-lookup"><span data-stu-id="299ef-365">System.Text.Encoding</span></span>](xref:System.Text.Encoding)





