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
# <a name="mailbnfhelper-class"></a>Classe MailBnfHelper

Contiene metodi di utilità per l'analisi di stringhe in formato messaggio Internet. Questa classe non può essere ereditata.

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> Questa classe è interna e non è destinata all'uso diretto nel codice.
>
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="ascii7bitmaxvalue-field"></a>Campo Ascii7bitMaxValue

Rappresenta il valore ASCII massimo a 7 bit.

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a>Campo aText

Rappresenta i caratteri consentiti negli atomi.

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a>Campo CR

Rappresenta il carattere di ritorno a capo.

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a>Campo CTEXT

Rappresenta i caratteri consentiti all'interno di commenti.

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a>Campo punto

Rappresenta il carattere di arresto completo ( `.` ).

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a>Campo di

Rappresenta il carattere che specifica la fine di un commento.

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a>Campo LF

Rappresenta il carattere di avanzamento riga.

```csharp
internal static readonly char LF
```

## <a name="space-field"></a>Campo spazio

Rappresenta il carattere spazio.

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a>Campo StartComment

Rappresenta il carattere che specifica l'inizio di un commento.

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a>Campo Tab

Rappresenta il carattere di tabulazione.

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)
