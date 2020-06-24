---
title: Classe QuotedPairReader (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.QuotedPairReader
- System.Net.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 9b0bf835a34eecc651894f4336648b73a81b665c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990375"
---
# <a name="quotedpairreader-class"></a><span data-ttu-id="3433b-102">Classe QuotedPairReader</span><span class="sxs-lookup"><span data-stu-id="3433b-102">QuotedPairReader class</span></span>

<span data-ttu-id="3433b-103">Determina quali caratteri sono racchiusi tra virgolette (di escape) in una stringa racchiusa tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="3433b-103">Determines which characters are quoted (escaped) in a quoted string.</span></span> <span data-ttu-id="3433b-104">Questa classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="3433b-104">This class cannot be inherited.</span></span>

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> <span data-ttu-id="3433b-105">Questa classe è interna e non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="3433b-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3433b-106">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="3433b-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="countquotedchars-method"></a><span data-ttu-id="3433b-107">Metodo CountQuotedChars</span><span class="sxs-lookup"><span data-stu-id="3433b-107">CountQuotedChars method</span></span>

<span data-ttu-id="3433b-108">Conta il numero di caratteri racchiusi tra virgolette consecutive, incluse più barre rovesciate tra virgolette precedenti, nella stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="3433b-108">Counts the number of consecutive quoted characters, including multiple preceding quoted backslashes, in the specified string.</span></span> <span data-ttu-id="3433b-109">Ad esempio, data la stringa `a\\\b` e un indice di `4` , il metodo restituisce `4` , perché `b` è racchiuso tra virgolette, quindi le tre barre rovesciate precedenti.</span><span class="sxs-lookup"><span data-stu-id="3433b-109">For example, given the string `a\\\b` and an index of `4`, the method returns `4`, because `b` is quoted and so are the three preceding backslashes.</span></span>

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a><span data-ttu-id="3433b-110">Parametri</span><span class="sxs-lookup"><span data-stu-id="3433b-110">Parameters</span></span>

- <span data-ttu-id="3433b-111">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="3433b-111">`data` <xref:System.String></span></span>

  <span data-ttu-id="3433b-112">Stringa di dati in cui contare i caratteri tra virgolette consecutive.</span><span class="sxs-lookup"><span data-stu-id="3433b-112">The data string in which to count consecutive quoted characters.</span></span>

- <span data-ttu-id="3433b-113">`index` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="3433b-113">`index` <xref:System.Int32></span></span>

  <span data-ttu-id="3433b-114">Posizione nella stringa specificata fino a e inclusi i caratteri tra virgolette consecutive da contare.</span><span class="sxs-lookup"><span data-stu-id="3433b-114">The position in the specified string up to and including which consecutive quoted characters should be counted.</span></span>

- <span data-ttu-id="3433b-115">`permitUnicodeEscaping` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="3433b-115">`permitUnicodeEscaping` <xref:System.Boolean></span></span>

  <span data-ttu-id="3433b-116">`true`per consentire l'escape di caratteri Unicode; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="3433b-116">`true` to permit Unicode characters to be escaped; otherwise, `false`.</span></span>

### <a name="return-value"></a><span data-ttu-id="3433b-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3433b-117">Return value</span></span>

<xref:System.Int32?displayProperty=nameWithType>

<span data-ttu-id="3433b-118">`0`Se il carattere in corrispondenza dell'indice specificato non è preceduto da un carattere di escape; in caso contrario, il numero di caratteri racchiusi tra virgolette consecutive fino al carattere in `index` .</span><span class="sxs-lookup"><span data-stu-id="3433b-118">`0` if the character at the specified index is not escaped; otherwise, the number of consecutive quoted characters up to and including the character at `index`.</span></span>

### <a name="exceptions"></a><span data-ttu-id="3433b-119">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="3433b-119">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="3433b-120">Un carattere Unicode con escape è stato trovato ma non è consentito.</span><span class="sxs-lookup"><span data-stu-id="3433b-120">An escaped Unicode character was found but is not permitted.</span></span>

## <a name="requirements"></a><span data-ttu-id="3433b-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3433b-121">Requirements</span></span>

<span data-ttu-id="3433b-122">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3433b-122">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3433b-123">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="3433b-123">**Assembly:** System (in System.dll)</span></span>