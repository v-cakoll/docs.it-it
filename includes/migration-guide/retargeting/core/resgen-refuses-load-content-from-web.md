---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614520"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a>Resgen rifiuta di caricare il contenuto dal Web

#### <a name="details"></a>Dettagli

i file con estensione resx possono contenere input in formato binario. Se si tenta di utilizzare Resgen per caricare un file scaricato da un percorso non attendibile, non sarà possibile caricare l'input per impostazione predefinita.

#### <a name="suggestion"></a>Suggerimento

Gli utenti di Resgen che richiedono il caricamento di input in formato binario da percorsi non attendibili possono rimuovere il contrassegno del Web dal file di input o applicare lo stravaganza esplicita. Aggiungere l'impostazione del registro di sistema seguente per applicare il rifiuto esplicito a livello di computer: [HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft.netframework\sdk] &quot; AllowProcessOfUntrustedResourceFiles &quot; = &quot; true&quot;

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |
