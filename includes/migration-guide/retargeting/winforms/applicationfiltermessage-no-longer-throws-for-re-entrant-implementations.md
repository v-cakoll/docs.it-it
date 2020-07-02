---
ms.openlocfilehash: 9b184f54650d2efb31ec66f443198b19ceaeb5f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614473"
---
### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Application.FilterMessage non genera più un'eccezione per le implementazioni rientranti di IMessageFilter.PreFilterMessage

#### <a name="details"></a>Dettagli

Prima di .NET Framework 4.6.1, una chiamata a <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> con un <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> che chiamava <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> o <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> (contemporaneamente alla chiamata a <xref:System.Windows.Forms.Application.DoEvents>) avrebbe causato una <xref:System.IndexOutOfRangeException?displayProperty=fullName>.<p/>A partire dalle applicazioni destinate a .NET Framework 4.6.1, questa eccezione non viene più generata e si possono usare filtri rientranti come descritto in precedenza.

#### <a name="suggestion"></a>Suggerimento

Tenere presente che <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> non genererà più un'eccezione per il comportamento <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> rientrante descritto in precedenza. Questa condizione influisce solo sulle applicazioni destinate a .NET Framework 4.6.1. Le app destinate a .NET Framework 4.6.1 possono rifiutare esplicitamente questa modifica (o le app destinate a versioni precedenti possono acconsentire esplicitamente) usando l'opzione di compatibilità [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation).

| Nome          | Valore       |
|:--------------|:------------|
| Scope         | Microsoft Edge        |
| Version       | 4.6.1       |
| Type          | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType>
