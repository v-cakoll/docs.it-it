---
title: Classe MailAddressParser (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051350"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="4df1e-102">Classe MailAddressParser</span><span class="sxs-lookup"><span data-stu-id="4df1e-102">MailAddressParser class</span></span>

<span data-ttu-id="4df1e-103">Analizza gli indirizzi di posta elettronica come descritto in RFC 2822.</span><span class="sxs-lookup"><span data-stu-id="4df1e-103">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="4df1e-104">Questa classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="4df1e-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="4df1e-105">Questa classe è interna e non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="4df1e-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4df1e-106">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="4df1e-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="4df1e-107">Metodo ParseAddress</span><span class="sxs-lookup"><span data-stu-id="4df1e-107">ParseAddress method</span></span>

<span data-ttu-id="4df1e-108">Analizza un singolo indirizzo di posta elettronica dalla stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="4df1e-108">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="4df1e-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="4df1e-109">Parameters</span></span>

<span data-ttu-id="4df1e-110">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="4df1e-110">`data` <xref:System.String></span></span>

<span data-ttu-id="4df1e-111">Stringa che contiene un indirizzo di posta elettronica da analizzare.</span><span class="sxs-lookup"><span data-stu-id="4df1e-111">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="4df1e-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4df1e-112">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="4df1e-113">Un indirizzo di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="4df1e-113">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="4df1e-114">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="4df1e-114">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="4df1e-115">L'indirizzo di posta elettronica non è valido.</span><span class="sxs-lookup"><span data-stu-id="4df1e-115">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="4df1e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4df1e-116">Requirements</span></span>

<span data-ttu-id="4df1e-117">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4df1e-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4df1e-118">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="4df1e-118">**Assembly:** System (in System.dll)</span></span>
