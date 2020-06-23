---
title: Classe MailAddressParser (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.MailAddressParser
- System.Net.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 2c17970614ff9b6f1e6793a064a956da7248d693
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990387"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="7dc5c-102">Classe MailAddressParser</span><span class="sxs-lookup"><span data-stu-id="7dc5c-102">MailAddressParser class</span></span>

<span data-ttu-id="7dc5c-103">Analizza gli indirizzi di posta elettronica come descritto in RFC 2822.</span><span class="sxs-lookup"><span data-stu-id="7dc5c-103">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="7dc5c-104">Questa classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="7dc5c-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="7dc5c-105">Questa classe è interna e non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="7dc5c-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="7dc5c-106">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="7dc5c-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="7dc5c-107">Metodo ParseAddress</span><span class="sxs-lookup"><span data-stu-id="7dc5c-107">ParseAddress method</span></span>

<span data-ttu-id="7dc5c-108">Analizza un singolo indirizzo di posta elettronica dalla stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="7dc5c-108">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="7dc5c-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="7dc5c-109">Parameters</span></span>

<span data-ttu-id="7dc5c-110">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7dc5c-110">`data` <xref:System.String></span></span>

<span data-ttu-id="7dc5c-111">Stringa che contiene un indirizzo di posta elettronica da analizzare.</span><span class="sxs-lookup"><span data-stu-id="7dc5c-111">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="7dc5c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7dc5c-112">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="7dc5c-113">Un indirizzo di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="7dc5c-113">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="7dc5c-114">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="7dc5c-114">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="7dc5c-115">L'indirizzo di posta elettronica non è valido.</span><span class="sxs-lookup"><span data-stu-id="7dc5c-115">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="7dc5c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7dc5c-116">Requirements</span></span>

<span data-ttu-id="7dc5c-117">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7dc5c-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7dc5c-118">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="7dc5c-118">**Assembly:** System (in System.dll)</span></span>
