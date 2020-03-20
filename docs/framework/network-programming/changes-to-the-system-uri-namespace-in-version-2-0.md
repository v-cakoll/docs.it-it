---
title: Modifiche apportate allo spazio dei nomi System.Uri nella versione 2.0
ms.date: 03/30/2017
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
ms.openlocfilehash: 987010b8367069e8089df3f809d23f258bb68f2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642763"
---
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a><span data-ttu-id="b426c-102">Modifiche apportate allo spazio dei nomi System.Uri nella versione 2.0</span><span class="sxs-lookup"><span data-stu-id="b426c-102">Changes to the System.Uri namespace in version 2.0</span></span>

<span data-ttu-id="b426c-103">Alla classe <xref:System.Uri?displayProperty=nameWithType> sono state apportate alcune modifiche</span><span class="sxs-lookup"><span data-stu-id="b426c-103">Several changes were made to the <xref:System.Uri?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="b426c-104">allo scopo di correggerne il comportamento nonché di aumentarne le possibilità d'utilizzo e il livello di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b426c-104">These changes fixed incorrect behavior, enhanced usability, and enhanced security.</span></span>

## <a name="obsolete-and-deprecated-members"></a><span data-ttu-id="b426c-105">Membri obsoleti e deprecati</span><span class="sxs-lookup"><span data-stu-id="b426c-105">Obsolete and deprecated Members</span></span>

 <span data-ttu-id="b426c-106">Costruttori:</span><span class="sxs-lookup"><span data-stu-id="b426c-106">Constructors:</span></span>

- <span data-ttu-id="b426c-107">Tutti i costruttori che accettano `dontEscape` come parametro.</span><span class="sxs-lookup"><span data-stu-id="b426c-107">All constructors that have a `dontEscape` parameter.</span></span>

 <span data-ttu-id="b426c-108">Metodi:</span><span class="sxs-lookup"><span data-stu-id="b426c-108">Methods:</span></span>

- <xref:System.Uri.CheckSecurity%2A>

- <xref:System.Uri.Escape%2A>

- <xref:System.Uri.Canonicalize%2A>

- <xref:System.Uri.Parse%2A>

- <xref:System.Uri.IsReservedCharacter%2A>

- <xref:System.Uri.IsBadFileSystemCharacter%2A>

- <xref:System.Uri.IsExcludedCharacter%2A>

- <xref:System.Uri.EscapeString%2A>

## <a name="changes"></a><span data-ttu-id="b426c-109">Modifiche</span><span class="sxs-lookup"><span data-stu-id="b426c-109">Changes</span></span>

- <span data-ttu-id="b426c-110">Nel caso di schemi URI in cui è notoriamente assente una parte relativa a query (file, ftp e altri), il punto interrogativo (?) deve essere sempre preceduto da un carattere di escape e non viene considerato come inizio di una parte <xref:System.Uri.Query%2A>.</span><span class="sxs-lookup"><span data-stu-id="b426c-110">For URI schemes that are known to not have a query part (file, ftp, and others), the '?' character is always escaped and is not considered the beginning of a <xref:System.Uri.Query%2A> part.</span></span>

- <span data-ttu-id="b426c-111">Per gli URI di file impliciti nel formato `c:\directory\file@name.txt`, il cancelletto (#) viene sempre preceduto da un carattere di escape tranne nei casi in cui è richiesta l'assenza totale di caratteri di escape oppure <xref:System.Uri.LocalPath%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="b426c-111">For implicit file URIs (of the form `c:\directory\file@name.txt`), the fragment character ('#') is always escaped unless full unescaping is requested or <xref:System.Uri.LocalPath%2A> is `true`.</span></span>

- <span data-ttu-id="b426c-112">Il supporto per nomi host UNC non è più disponibile. Per la rappresentazione dei nomi host internazionali è ora stata adottata la specifica IDN.</span><span class="sxs-lookup"><span data-stu-id="b426c-112">UNC hostname support was removed; the IDN specification for representing international hostnames was adopted.</span></span>

- <span data-ttu-id="b426c-113"><xref:System.Uri.LocalPath%2A> restituisce sempre una stringa senza alcun carattere di escape.</span><span class="sxs-lookup"><span data-stu-id="b426c-113"><xref:System.Uri.LocalPath%2A> always returns a completely unescaped string.</span></span>

- <span data-ttu-id="b426c-114"><xref:System.Uri.ToString%2A> non rimuove l'eventuale carattere di escape che precede il segno di percentuale (%), il punto interrogativo (?) o il cancelletto (#).</span><span class="sxs-lookup"><span data-stu-id="b426c-114"><xref:System.Uri.ToString%2A> does not unescape an escaped '%', '?', or '#' character.</span></span>

- <span data-ttu-id="b426c-115"><xref:System.Uri.Equals%2A> include ora la parte <xref:System.Uri.Query%2A> nel controllo di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="b426c-115"><xref:System.Uri.Equals%2A> now includes the <xref:System.Uri.Query%2A> part in the equality check.</span></span>

- <span data-ttu-id="b426c-116">Gli operatori == e != sono sottoposti a override e collegati al metodo <xref:System.Uri.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="b426c-116">Operators "==" and "!=" are overridden and linked to the <xref:System.Uri.Equals%2A> method.</span></span>

- <span data-ttu-id="b426c-117"><xref:System.Uri.IsLoopback%2A> è ora in grado di generare risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="b426c-117"><xref:System.Uri.IsLoopback%2A> now produces consistent results.</span></span>

- <span data-ttu-id="b426c-118">L'URI "`file:///path`" non viene più convertito in `file://path`.</span><span class="sxs-lookup"><span data-stu-id="b426c-118">The URI "`file:///path`" is no longer translated into `file://path`.</span></span>

- <span data-ttu-id="b426c-119">Il cancelletto (#) viene ora riconosciuto come carattere di terminazione di nome host.</span><span class="sxs-lookup"><span data-stu-id="b426c-119">"#" is now recognized as a host name terminator.</span></span> <span data-ttu-id="b426c-120">Vale a dire, `http://contoso.com#fragment` diventa `http://contoso.com/#fragment`.</span><span class="sxs-lookup"><span data-stu-id="b426c-120">That is, `http://contoso.com#fragment` is now converted to `http://contoso.com/#fragment`.</span></span>

- <span data-ttu-id="b426c-121">È stato corretto un bug relativo alla combinazione di un URI di base con un frammento.</span><span class="sxs-lookup"><span data-stu-id="b426c-121">A bug when combining a base URI with a fragment has been fixed.</span></span>

- <span data-ttu-id="b426c-122">È stato corretto un bug in <xref:System.Uri.HostNameType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b426c-122">A bug in <xref:System.Uri.HostNameType%2A> is fixed.</span></span>

- <span data-ttu-id="b426c-123">È stato corretto un bug nell'analisi NNTP.</span><span class="sxs-lookup"><span data-stu-id="b426c-123">A bug in NNTP parsing is fixed.</span></span>

- <span data-ttu-id="b426c-124">Un URI nel formato HTTP:contoso.com genera ora un'eccezione di analisi.</span><span class="sxs-lookup"><span data-stu-id="b426c-124">A URI of the form HTTP:contoso.com now throws a parsing exception.</span></span>

- <span data-ttu-id="b426c-125">.NET Framework gestisce correttamente le informazioni utente in un URI.</span><span class="sxs-lookup"><span data-stu-id="b426c-125">The Framework correctly handles userinfo in a URI.</span></span>

- <span data-ttu-id="b426c-126">La compressione dei percorsi URI è stata corretta in modo da impedire a un URI interrotto di attraversare il file system al di sopra della radice.</span><span class="sxs-lookup"><span data-stu-id="b426c-126">URI path compression is fixed so that a broken URI cannot traverse the file system above the root.</span></span>

## <a name="see-also"></a><span data-ttu-id="b426c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b426c-127">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
