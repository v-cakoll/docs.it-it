---
title: Classe MailBnfHelper (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 86c98726a7886285917b6be8c7631ca1e9e425e6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990368"
---
# <a name="mailbnfhelper-class"></a><span data-ttu-id="187dd-102">Classe MailBnfHelper</span><span class="sxs-lookup"><span data-stu-id="187dd-102">MailBnfHelper class</span></span>

<span data-ttu-id="187dd-103">Contiene metodi di utilità per l'analisi di stringhe in formato messaggio Internet.</span><span class="sxs-lookup"><span data-stu-id="187dd-103">Contains utility methods for parsing internet message-formatted strings.</span></span> <span data-ttu-id="187dd-104">Questa classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="187dd-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> <span data-ttu-id="187dd-105">Questa classe è interna e non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="187dd-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="187dd-106">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="187dd-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="ascii7bitmaxvalue-field"></a><span data-ttu-id="187dd-107">Campo Ascii7bitMaxValue</span><span class="sxs-lookup"><span data-stu-id="187dd-107">Ascii7bitMaxValue field</span></span>

<span data-ttu-id="187dd-108">Rappresenta il valore ASCII massimo a 7 bit.</span><span class="sxs-lookup"><span data-stu-id="187dd-108">Represents the maximum 7-bit Ascii value.</span></span>

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a><span data-ttu-id="187dd-109">Campo aText</span><span class="sxs-lookup"><span data-stu-id="187dd-109">Atext field</span></span>

<span data-ttu-id="187dd-110">Rappresenta i caratteri consentiti negli atomi.</span><span class="sxs-lookup"><span data-stu-id="187dd-110">Represents the characters allowed in atoms.</span></span>

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a><span data-ttu-id="187dd-111">Campo CR</span><span class="sxs-lookup"><span data-stu-id="187dd-111">CR field</span></span>

<span data-ttu-id="187dd-112">Rappresenta il carattere di ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="187dd-112">Represents the carriage-return character.</span></span>

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a><span data-ttu-id="187dd-113">Campo CTEXT</span><span class="sxs-lookup"><span data-stu-id="187dd-113">Ctext field</span></span>

<span data-ttu-id="187dd-114">Rappresenta i caratteri consentiti all'interno di commenti.</span><span class="sxs-lookup"><span data-stu-id="187dd-114">Represents the characters allowed inside of comments.</span></span>

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a><span data-ttu-id="187dd-115">Campo punto</span><span class="sxs-lookup"><span data-stu-id="187dd-115">Dot field</span></span>

<span data-ttu-id="187dd-116">Rappresenta il carattere di arresto completo ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="187dd-116">Represents the full-stop character (`.`).</span></span>

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a><span data-ttu-id="187dd-117">Campo di</span><span class="sxs-lookup"><span data-stu-id="187dd-117">EndComment field</span></span>

<span data-ttu-id="187dd-118">Rappresenta il carattere che specifica la fine di un commento.</span><span class="sxs-lookup"><span data-stu-id="187dd-118">Represents the character that specifies the end of a comment.</span></span>

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a><span data-ttu-id="187dd-119">Campo LF</span><span class="sxs-lookup"><span data-stu-id="187dd-119">LF field</span></span>

<span data-ttu-id="187dd-120">Rappresenta il carattere di avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="187dd-120">Represents the line-feed character.</span></span>

```csharp
internal static readonly char LF
```

## <a name="space-field"></a><span data-ttu-id="187dd-121">Campo spazio</span><span class="sxs-lookup"><span data-stu-id="187dd-121">Space field</span></span>

<span data-ttu-id="187dd-122">Rappresenta il carattere spazio.</span><span class="sxs-lookup"><span data-stu-id="187dd-122">Represents the space character.</span></span>

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a><span data-ttu-id="187dd-123">Campo StartComment</span><span class="sxs-lookup"><span data-stu-id="187dd-123">StartComment field</span></span>

<span data-ttu-id="187dd-124">Rappresenta il carattere che specifica l'inizio di un commento.</span><span class="sxs-lookup"><span data-stu-id="187dd-124">Represents the character that specifies the start of a comment.</span></span>

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a><span data-ttu-id="187dd-125">Campo Tab</span><span class="sxs-lookup"><span data-stu-id="187dd-125">Tab field</span></span>

<span data-ttu-id="187dd-126">Rappresenta il carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="187dd-126">Represents the tab character.</span></span>

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a><span data-ttu-id="187dd-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="187dd-127">Requirements</span></span>

<span data-ttu-id="187dd-128">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="187dd-128">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="187dd-129">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="187dd-129">**Assembly:** System (in System.dll)</span></span>
