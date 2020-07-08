---
title: Classe QuotedPairReader (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.QuotedPairReader
- System.Net.Mail.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 898c6e9d2d5dd02f3d5f9c096ad470b5dd445d1d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051311"
---
# <a name="quotedpairreader-class"></a>Classe QuotedPairReader

Determina quali caratteri sono racchiusi tra virgolette (di escape) in una stringa racchiusa tra virgolette. Questa classe non può essere ereditata.

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> Questa classe è interna e non è destinata all'uso diretto nel codice.
>
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="countquotedchars-method"></a>Metodo CountQuotedChars

Conta il numero di caratteri racchiusi tra virgolette consecutive, incluse più barre rovesciate tra virgolette precedenti, nella stringa specificata. Ad esempio, data la stringa `a\\\b` e un indice di `4` , il metodo restituisce `4` , perché `b` è racchiuso tra virgolette, quindi le tre barre rovesciate precedenti.

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a>Parametri

- `data` <xref:System.String>

  Stringa di dati in cui contare i caratteri tra virgolette consecutive.

- `index` <xref:System.Int32>

  Posizione nella stringa specificata fino a e inclusi i caratteri tra virgolette consecutive da contare.

- `permitUnicodeEscaping` <xref:System.Boolean>

  `true`per consentire l'escape di caratteri Unicode; in caso contrario, `false` .

### <a name="return-value"></a>Valore restituito

<xref:System.Int32?displayProperty=nameWithType>

`0`Se il carattere in corrispondenza dell'indice specificato non è preceduto da un carattere di escape; in caso contrario, il numero di caratteri racchiusi tra virgolette consecutive fino al carattere in `index` .

### <a name="exceptions"></a>Eccezioni

<xref:System.FormatException?displayProperty=nameWithType>

Un carattere Unicode con escape è stato trovato ma non è consentito.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)
