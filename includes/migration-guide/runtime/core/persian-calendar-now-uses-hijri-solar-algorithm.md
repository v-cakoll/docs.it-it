---
ms.openlocfilehash: e4d9efe7d2a06a1e501b070c23184dcd913dba71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621283"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>Il calendario persiano ora usa l'algoritmo solare Hijri

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6, la classe <xref:System.Globalization.PersianCalendar?displayProperty=fullName> usa l'algoritmo solare Hijri. La conversione di date tra il calendario <xref:System.Globalization.PersianCalendar?displayProperty=fullName> e altri calendari può produrre risultati leggermente diversi a partire da .NET Framework 4.6 per le date precedenti al 1800 o successive al 2023 (calendario gregoriano). Inoltre, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> è ora <code>March 22, 0622</code> invece di <code>March 21, 0622</code>.

#### <a name="suggestion"></a>Suggerimento

Tenere presente che alcune date precedenti o successive potrebbero essere leggermente diverse quando si usa PersianCalendar in .NET Framework 4.6. Inoltre, quando si serializzano le date tra processi che possono essere eseguiti in versioni diverse di .NET Framework, evitare di archiviarle come stringhe di data PersianCalendar, perché tali valori potrebbero essere diversi.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
