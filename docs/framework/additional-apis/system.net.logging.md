---
title: Classe Logging (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ad85fdd41252ed147eb5fe1a9db029db046d720c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990388"
---
# <a name="logging-class"></a>Classe Logging

Fornisce funzionalità di registrazione della traccia.

```csharp
internal class Logging
```

> [!WARNING]
> Questa classe è interna e non è destinata all'uso diretto nel codice.
>
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="associate-method"></a>Metodo associate

Registra informazioni che due oggetti sono associati tra loro.

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `objA` <xref:System.Object>

  Oggetto da associare a `objB` .

- `objB` <xref:System.Object>

  Oggetto da associare a `objA` .

## <a name="entertracesource-object-string-string-method"></a>Metodo Enter (TraceSource, Object, String, String)

Registra l'ingresso a un metodo.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.Object>

  Oggetto su cui è stato chiamato il metodo.

- `method` <xref:System.String>

  Metodo immesso.

- `param` <xref:System.String>

  Parametri passati al metodo.

## <a name="entertracesource-object-string-object-method"></a>Metodo Enter (TraceSource, Object, String, Object)

Registra l'ingresso a un metodo.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.Object>

  Oggetto su cui è stato chiamato il metodo.

- `method` <xref:System.String>

  Metodo immesso.

- `paramObject` <xref:System.Object>

  Parametri passati al metodo.

## <a name="entertracesource-string-string-string-method"></a>Metodo Enter (TraceSource, String, String, String)

Registra l'ingresso a un metodo.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.String>

  Oggetto su cui è stato chiamato il metodo.

- `method` <xref:System.String>

  Metodo immesso.

- `param` <xref:System.String>

  Parametri passati al metodo.

## <a name="entertracesource-string-string-object-method"></a>Metodo Enter (TraceSource, String, String, Object)

Registra l'ingresso a un metodo.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.String>

  Oggetto su cui è stato chiamato il metodo.

- `method` <xref:System.String>

  Metodo immesso.

- `paramObject` <xref:System.Object>

  Parametri passati al metodo.

## <a name="entertracesource-string-string-method"></a>Metodo Enter (TraceSource, String, String)

Registra l'ingresso a un metodo.

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `method` <xref:System.String>

  Metodo immesso.

- `parameters` <xref:System.String>

  Parametri passati al metodo.

## <a name="entertracesource-string-method"></a>Metodo Enter (TraceSource, String)

Registra l'ingresso a un metodo.

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `msg` <xref:System.String>

  Messaggio di ingresso da registrare nell'origine di traccia.

## <a name="exception-method"></a>Exception (metodo)

Registra un'eccezione e ripristina il rientro.

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.Object>

  Oggetto in cui è stato chiamato il metodo che ha generato un'eccezione.

- `method` <xref:System.String>

  Metodo che ha generato l'eccezione.

- `e` <xref:System.Exception>

  L'eccezione generata.

## <a name="exittracesource-object-string-object-method"></a>Metodo Exit (TraceSource, Object, String, Object)

Il log viene chiuso da una funzione.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.Object>

  Oggetto su cui è stato chiamato il metodo.

- `method` <xref:System.String>

  Metodo che viene terminato.

- `retObject` <xref:System.Object>

  Valore restituito dal metodo.

## <a name="exittracesource-string-string-object-method"></a>Metodo Exit (TraceSource, String, String, Object)

Il log viene chiuso da una funzione.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.String>

  Oggetto su cui è stato chiamato il metodo.

- `method` <xref:System.String>

  Metodo che viene terminato.

- `retObject` <xref:System.Object>

  Valore restituito dal metodo.

## <a name="exittracesource-object-string-string-method"></a>Metodo Exit (TraceSource, Object, String, String)

Il log viene chiuso da una funzione.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.Object>

  Oggetto su cui è stato chiamato il metodo.

- `method` <xref:System.String>

  Metodo che viene terminato.

- `retValue` <xref:System.String>

  Valore restituito dal metodo.

## <a name="exittracesource-string-string-string-method"></a>Metodo Exit (TraceSource, String, String, String)

Il log viene chiuso da una funzione.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `obj` <xref:System.String>

  Oggetto su cui è stato chiamato il metodo.

- `method` <xref:System.String>

  Metodo che viene terminato.

- `retValue` <xref:System.String>

  Valore restituito dal metodo.

## <a name="exittracesource-string-string-method"></a>Metodo Exit (TraceSource, String, String)

Il log viene chiuso da una funzione.

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `method` <xref:System.String>

  Metodo che viene terminato.

- `parameters` <xref:System.String>

  Parametri passati al metodo che viene terminato.

## <a name="exittracesource-string-method"></a>Metodo Exit (TraceSource, String)

Il log viene chiuso da una funzione.

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>Parametri

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origine di traccia in cui registrare l'evento.

- `msg` <xref:System.String>

  Messaggio di uscita da registrare nell'origine di traccia.

## <a name="http-property"></a>Proprietà http

Ottiene l'origine di traccia per "System .NET. http".

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a>Valore proprietà

<xref:System.Diagnostics.TraceSource>\
Origine di traccia per "System .NET. http" o `null` se la registrazione non è abilitata.

## <a name="on-property"></a>On (proprietà)

Ottiene un valore che indica se la registrazione è abilitata.

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a>Valore proprietà

<xref:System.Boolean>\
`true` se la registrazione è abilitata; in caso contrario, `false`.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)
