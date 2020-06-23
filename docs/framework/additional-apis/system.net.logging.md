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
# <a name="logging-class"></a><span data-ttu-id="7b3f4-102">Classe Logging</span><span class="sxs-lookup"><span data-stu-id="7b3f4-102">Logging class</span></span>

<span data-ttu-id="7b3f4-103">Fornisce funzionalità di registrazione della traccia.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-103">Provides trace logging functionality.</span></span>

```csharp
internal class Logging
```

> [!WARNING]
> <span data-ttu-id="7b3f4-104">Questa classe è interna e non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-104">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="7b3f4-105">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-105">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="associate-method"></a><span data-ttu-id="7b3f4-106">Metodo associate</span><span class="sxs-lookup"><span data-stu-id="7b3f4-106">Associate method</span></span>

<span data-ttu-id="7b3f4-107">Registra informazioni che due oggetti sono associati tra loro.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-107">Logs information that two objects are associated with each other.</span></span>

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-108">Parameters</span></span>

- <span data-ttu-id="7b3f4-109">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-109">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-110">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-110">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-111">`objA` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-111">`objA` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-112">Oggetto da associare a `objB` .</span><span class="sxs-lookup"><span data-stu-id="7b3f4-112">The object to associate with `objB`.</span></span>

- <span data-ttu-id="7b3f4-113">`objB` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-113">`objB` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-114">Oggetto da associare a `objA` .</span><span class="sxs-lookup"><span data-stu-id="7b3f4-114">The object to associate with `objA`.</span></span>

## <a name="entertracesource-object-string-string-method"></a><span data-ttu-id="7b3f4-115">Metodo Enter (TraceSource, Object, String, String)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-115">Enter(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="7b3f4-116">Registra l'ingresso a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-116">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-117">Parameters</span></span>

- <span data-ttu-id="7b3f4-118">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-118">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-119">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-119">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-120">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-120">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-121">Oggetto su cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-121">The object that the method was called on.</span></span>

- <span data-ttu-id="7b3f4-122">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-122">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-123">Metodo immesso.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-123">The method that is being entered.</span></span>

- <span data-ttu-id="7b3f4-124">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-124">`param` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-125">Parametri passati al metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-125">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-object-string-object-method"></a><span data-ttu-id="7b3f4-126">Metodo Enter (TraceSource, Object, String, Object)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-126">Enter(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="7b3f4-127">Registra l'ingresso a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-127">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-128">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-128">Parameters</span></span>

- <span data-ttu-id="7b3f4-129">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-129">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-130">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-130">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-131">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-131">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-132">Oggetto su cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-132">The object that the method was called on.</span></span>

- <span data-ttu-id="7b3f4-133">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-133">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-134">Metodo immesso.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-134">The method that is being entered.</span></span>

- <span data-ttu-id="7b3f4-135">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-135">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-136">Parametri passati al metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-136">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-string-method"></a><span data-ttu-id="7b3f4-137">Metodo Enter (TraceSource, String, String, String)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-137">Enter(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="7b3f4-138">Registra l'ingresso a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-138">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-139">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-139">Parameters</span></span>

- <span data-ttu-id="7b3f4-140">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-140">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-141">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-141">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-142">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-142">`obj` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-143">Oggetto su cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-143">The object that the method was called on.</span></span>

- <span data-ttu-id="7b3f4-144">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-144">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-145">Metodo immesso.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-145">The method that is being entered.</span></span>

- <span data-ttu-id="7b3f4-146">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-146">`param` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-147">Parametri passati al metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-147">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-object-method"></a><span data-ttu-id="7b3f4-148">Metodo Enter (TraceSource, String, String, Object)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-148">Enter(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="7b3f4-149">Registra l'ingresso a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-149">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-150">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-150">Parameters</span></span>

- <span data-ttu-id="7b3f4-151">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-151">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-152">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-152">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-153">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-153">`obj` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-154">Oggetto su cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-154">The object that the method was called on.</span></span>

- <span data-ttu-id="7b3f4-155">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-155">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-156">Metodo immesso.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-156">The method that is being entered.</span></span>

- <span data-ttu-id="7b3f4-157">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-157">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-158">Parametri passati al metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-158">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-method"></a><span data-ttu-id="7b3f4-159">Metodo Enter (TraceSource, String, String)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-159">Enter(TraceSource, string, string) method</span></span>

<span data-ttu-id="7b3f4-160">Registra l'ingresso a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-160">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-161">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-161">Parameters</span></span>

- <span data-ttu-id="7b3f4-162">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-162">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-163">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-163">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-164">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-164">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-165">Metodo immesso.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-165">The method that is being entered.</span></span>

- <span data-ttu-id="7b3f4-166">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-166">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-167">Parametri passati al metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-167">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-method"></a><span data-ttu-id="7b3f4-168">Metodo Enter (TraceSource, String)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-168">Enter(TraceSource, string) method</span></span>

<span data-ttu-id="7b3f4-169">Registra l'ingresso a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-169">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-170">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-170">Parameters</span></span>

- <span data-ttu-id="7b3f4-171">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-171">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-172">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-172">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-173">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-173">`msg` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-174">Messaggio di ingresso da registrare nell'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-174">The entrance message to log to the trace source.</span></span>

## <a name="exception-method"></a><span data-ttu-id="7b3f4-175">Exception (metodo)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-175">Exception method</span></span>

<span data-ttu-id="7b3f4-176">Registra un'eccezione e ripristina il rientro.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-176">Logs an exception and restores indentation.</span></span>

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-177">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-177">Parameters</span></span>

- <span data-ttu-id="7b3f4-178">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-178">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-179">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-179">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-180">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-180">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-181">Oggetto in cui è stato chiamato il metodo che ha generato un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-181">The object that the method that threw an exception was called on.</span></span>

- <span data-ttu-id="7b3f4-182">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-182">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-183">Metodo che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-183">The method that threw the exception.</span></span>

- <span data-ttu-id="7b3f4-184">`e` <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="7b3f4-184">`e` <xref:System.Exception></span></span>

  <span data-ttu-id="7b3f4-185">L'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-185">The exception that was thrown.</span></span>

## <a name="exittracesource-object-string-object-method"></a><span data-ttu-id="7b3f4-186">Metodo Exit (TraceSource, Object, String, Object)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-186">Exit(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="7b3f4-187">Il log viene chiuso da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-187">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-188">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-188">Parameters</span></span>

- <span data-ttu-id="7b3f4-189">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-189">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-190">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-190">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-191">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-191">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-192">Oggetto su cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-192">The object that the method was called on.</span></span>

- <span data-ttu-id="7b3f4-193">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-193">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-194">Metodo che viene terminato.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-194">The method that is being exited.</span></span>

- <span data-ttu-id="7b3f4-195">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-195">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-196">Valore restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-196">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-object-method"></a><span data-ttu-id="7b3f4-197">Metodo Exit (TraceSource, String, String, Object)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-197">Exit(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="7b3f4-198">Il log viene chiuso da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-198">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-199">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-199">Parameters</span></span>

- <span data-ttu-id="7b3f4-200">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-200">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-201">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-201">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-202">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-202">`obj` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-203">Oggetto su cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-203">The object that the method was called on.</span></span>

- <span data-ttu-id="7b3f4-204">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-204">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-205">Metodo che viene terminato.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-205">The method that is being exited.</span></span>

- <span data-ttu-id="7b3f4-206">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-206">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-207">Valore restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-207">The value that's being returned by the method.</span></span>

## <a name="exittracesource-object-string-string-method"></a><span data-ttu-id="7b3f4-208">Metodo Exit (TraceSource, Object, String, String)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-208">Exit(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="7b3f4-209">Il log viene chiuso da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-209">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-210">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-210">Parameters</span></span>

- <span data-ttu-id="7b3f4-211">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-211">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-212">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-212">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-213">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="7b3f4-213">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="7b3f4-214">Oggetto su cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-214">The object that the method was called on.</span></span>

- <span data-ttu-id="7b3f4-215">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-215">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-216">Metodo che viene terminato.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-216">The method that is being exited.</span></span>

- <span data-ttu-id="7b3f4-217">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-217">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-218">Valore restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-218">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-string-method"></a><span data-ttu-id="7b3f4-219">Metodo Exit (TraceSource, String, String, String)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-219">Exit(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="7b3f4-220">Il log viene chiuso da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-220">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-221">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-221">Parameters</span></span>

- <span data-ttu-id="7b3f4-222">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-222">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-223">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-223">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-224">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-224">`obj` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-225">Oggetto su cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-225">The object that the method was called on.</span></span>

- <span data-ttu-id="7b3f4-226">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-226">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-227">Metodo che viene terminato.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-227">The method that is being exited.</span></span>

- <span data-ttu-id="7b3f4-228">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-228">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-229">Valore restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-229">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-method"></a><span data-ttu-id="7b3f4-230">Metodo Exit (TraceSource, String, String)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-230">Exit(TraceSource, string, string) method</span></span>

<span data-ttu-id="7b3f4-231">Il log viene chiuso da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-231">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-232">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-232">Parameters</span></span>

- <span data-ttu-id="7b3f4-233">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-233">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-234">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-234">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-235">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-235">`method` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-236">Metodo che viene terminato.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-236">The method that is being exited.</span></span>

- <span data-ttu-id="7b3f4-237">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-237">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-238">Parametri passati al metodo che viene terminato.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-238">The parameters that were passed to the method that's being exited.</span></span>

## <a name="exittracesource-string-method"></a><span data-ttu-id="7b3f4-239">Metodo Exit (TraceSource, String)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-239">Exit(TraceSource, string) method</span></span>

<span data-ttu-id="7b3f4-240">Il log viene chiuso da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-240">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="7b3f4-241">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b3f4-241">Parameters</span></span>

- <span data-ttu-id="7b3f4-242">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="7b3f4-242">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="7b3f4-243">Origine di traccia in cui registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-243">The trace source to log the event to.</span></span>

- <span data-ttu-id="7b3f4-244">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="7b3f4-244">`msg` <xref:System.String></span></span>

  <span data-ttu-id="7b3f4-245">Messaggio di uscita da registrare nell'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-245">The exit message to log to the trace source.</span></span>

## <a name="http-property"></a><span data-ttu-id="7b3f4-246">Proprietà http</span><span class="sxs-lookup"><span data-stu-id="7b3f4-246">Http property</span></span>

<span data-ttu-id="7b3f4-247">Ottiene l'origine di traccia per "System .NET. http".</span><span class="sxs-lookup"><span data-stu-id="7b3f4-247">Gets the trace source for "System.Net.Http".</span></span>

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a><span data-ttu-id="7b3f4-248">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="7b3f4-248">Property value</span></span>

<xref:System.Diagnostics.TraceSource>\
<span data-ttu-id="7b3f4-249">Origine di traccia per "System .NET. http" o `null` se la registrazione non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-249">The trace source for "System.Net.Http", or `null` if logging is not enabled.</span></span>

## <a name="on-property"></a><span data-ttu-id="7b3f4-250">On (proprietà)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-250">On property</span></span>

<span data-ttu-id="7b3f4-251">Ottiene un valore che indica se la registrazione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-251">Gets a value that indicates whether logging is enabled.</span></span>

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a><span data-ttu-id="7b3f4-252">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="7b3f4-252">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="7b3f4-253">`true` se la registrazione è abilitata; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-253">`true` if logging is enabled; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b3f4-254">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b3f4-254">Requirements</span></span>

<span data-ttu-id="7b3f4-255">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7b3f4-255">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7b3f4-256">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-256">**Assembly:** System (in System.dll)</span></span>
