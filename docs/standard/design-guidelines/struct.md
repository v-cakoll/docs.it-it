---
title: Progettazione di struct
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: c6ac53014e048da3a90dd7b8e961176f61e90355
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290811"
---
# <a name="struct-design"></a>Progettazione di struct
Il tipo di valore generico è spesso definito struct, la relativa parola chiave C#. Questa sezione fornisce linee guida per la progettazione di struct generali.

 ❌Non fornire un costruttore senza parametri per uno struct.

 Seguendo questa guida, è possibile creare matrici di struct senza dover eseguire il costruttore in ogni elemento della matrice. Si noti che C# non consente struct con costruttori senza parametri.

 ❌NON definire tipi di valore modificabili.

 I tipi di valore modificabili presentano diversi problemi. Ad esempio, quando un getter di proprietà restituisce un tipo di valore, il chiamante riceve una copia. Poiché la copia viene creata in modo implicito, è possibile che gli sviluppatori non ritengano che stiano mutando la copia e non il valore originale. Inoltre, alcune lingue (linguaggi dinamici, in particolare) presentano problemi con i tipi di valore modificabili perché anche le variabili locali, quando vengono dereferenziate, causano la copia.

 ✔️ Verificare che uno stato in cui tutti i dati dell'istanza siano impostati su zero, false o null (se appropriato) sia valido.

 Ciò impedisce la creazione accidentale di istanze non valide quando viene creata una matrice degli struct.

 ✔️ implementano i <xref:System.IEquatable%601> tipi di valore.

 Il <xref:System.Object.Equals%2A?displayProperty=nameWithType> metodo sui tipi valore causa la conversione boxing e la relativa implementazione predefinita non è molto efficiente perché usa la reflection. <xref:System.IEquatable%601.Equals%2A>può avere prestazioni molto migliori e può essere implementato in modo che non provochi la conversione boxing.

 ❌Non estendere in modo esplicito <xref:System.ValueType> . In realtà, la maggior parte dei linguaggi impedisce questo problema.

 In generale, gli struct possono essere molto utili, ma devono essere usati solo per valori piccoli, singoli e non modificabili che non verranno sottoposto a Boxing di frequente.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](type.md)
- [Linee guida per la progettazione di Framework](index.md)
- [Scelta tra classi e struct](choosing-between-class-and-struct.md)
