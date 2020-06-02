---
title: Matrici
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: 30277507050091de6b1e9293401d61ac5e351a1f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280621"
---
# <a name="arrays"></a>Matrici
✔️ preferiscono usare le raccolte su matrici in API pubbliche. La sezione [Collections](guidelines-for-collections.md) fornisce informazioni dettagliate su come scegliere tra le raccolte e le matrici.

 ❌Non usare campi di matrice di sola lettura. Il campo stesso è di sola lettura e non può essere modificato, ma è possibile modificare gli elementi della matrice.

 ✔️ CONSIGLIABILE utilizzare matrici di matrici anziché matrici multidimensionali.

 Una matrice irregolare è una matrice con elementi che sono anche matrici. Le matrici che costituiscono gli elementi possono avere dimensioni diverse, causando uno spazio meno sprecato per alcuni set di dati (ad esempio, una matrice di tipo sparse) rispetto alle matrici multidimensionali. Inoltre, CLR ottimizza le operazioni sugli indici su matrici di matrici, in modo che possano presentare prestazioni di runtime migliori in alcuni scenari.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- <xref:System.Array>
- [Linee guida per la progettazione di Framework](index.md)
- [Linee guida sull'utilizzo](usage-guidelines.md)
