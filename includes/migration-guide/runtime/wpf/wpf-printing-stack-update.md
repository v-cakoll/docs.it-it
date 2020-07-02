---
ms.openlocfilehash: 5e2e8d1ec5d698d1c1649c2a0a1b4b77dbdf4022
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621280"
---
### <a name="wpf-printing-stack-update"></a>Aggiornamento dello stack di stampa WPF

#### <a name="details"></a>Dettagli

Le API di stampa di WPF che usano <xref:System.Printing.PrintQueue?displayProperty=fullName> ora chiamano l'API di gestione del pacchetto dei documenti di stampa di Windows invece dell'API di stampa XPS, ora deprecata. La modifica è stata apportata per ottimizzare la funzionalità. Né gli utenti né gli sviluppatori dovrebbero riscontrare modifiche nel comportamento o nell'uso dell'API. Il nuovo stack di stampa viene abilitato per impostazione predefinita durante l'esecuzione in Windows 10 Creators Update. Il vecchio stack di stampa continua a funzionare come in precedenza nelle versioni precedenti di Windows.

#### <a name="suggestion"></a>Suggerimento

Per usare lo stack precedente in Windows 10 Creators Update, impostare il valore <code>UseXpsOMPrinting</code> REG_DWORD della chiave del Registro di sistema <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> su <code>1</code>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.7|
|Type|Runtime|
