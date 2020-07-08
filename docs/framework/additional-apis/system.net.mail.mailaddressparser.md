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
# <a name="mailaddressparser-class"></a>Classe MailAddressParser

Analizza gli indirizzi di posta elettronica come descritto in RFC 2822. Questa classe non può essere ereditata.

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> Questa classe è interna e non è destinata all'uso diretto nel codice.
>
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="parseaddress-method"></a>Metodo ParseAddress

Analizza un singolo indirizzo di posta elettronica dalla stringa specificata.

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a>Parametri

`data` <xref:System.String>

Stringa che contiene un indirizzo di posta elettronica da analizzare.

### <a name="return-value"></a>Valore restituito

<xref:System.Net.Mail.MailAddress>

Un indirizzo di posta elettronica valido.

### <a name="exceptions"></a>Eccezioni

<xref:System.FormatException?displayProperty=nameWithType>

L'indirizzo di posta elettronica non è valido.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)
