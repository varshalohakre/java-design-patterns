---
title: "Modello di Anti-Corruption Layer in Java: Garantire l'Integrità del Sistema in presenza di Sistemi Legacy"
shortTitle: Anti-Corruption Layer
description: "Scopri come il modello di design Anti-Corruption Layer aiuta nel disaccoppiamento dei sottosistemi, prevenendo la corruzione dei dati e facilitando l'integrazione senza soluzione di continuità nelle applicazioni Java."
category: Integrazione
language: it
tag:
  - Architettura
  - Disaccoppiamento
  - Integrazione
  - Isolamento
  - Architettura a strati
  - Migrazione
  - Modernizzazione
  - Refactoring
  - Wrapping
---

## Anche conosciuto come

* ACL
* Layer di interfaccia
* Layer di traduzione

## Intento del Modello di Design Anti-Corruption Layer

L'Anti-Corruption Layer (ACL) è un modello di design cruciale nello sviluppo Java, particolarmente per l'integrazione dei sistemi e il mantenimento dell'integrità dei dati. Implementa un layer di facciata o adattatore tra diversi sottosistemi che non condividono la stessa semantica. Traduce tra diversi formati di dati e sistemi, assicurando che l'integrazione tra i sistemi non porti a corruzione della logica aziendale o dell'integrità dei dati.

## Spiegazione Dettagliata del Modello di Anti-Corruption Layer con Esempi del Mondo Reale

Esempio del mondo reale

> Questo esempio dimostra come l'Anti-Corruption Layer garantisca un'integrazione senza soluzione di continuità tra i sistemi legacy e le piattaforme moderne, fondamentale per mantenere l'integrità della logica aziendale durante la migrazione del sistema.
> 
> Immagina una grande azienda di vendita al dettaglio che sta trasferendo il proprio sistema di gestione dell'inventario da un vecchio software legacy a una nuova piattaforma moderna. Il sistema legacy è stato utilizzato per decenni e contiene regole aziendali complesse e formati di dati incompatibili con il nuovo sistema. Invece di connettere direttamente il nuovo sistema a quello legacy, l'azienda implementa un Anti-Corruption Layer (ACL).
> 
> L'ACL agisce come mediatore, traducendo e adattando i dati tra i due sistemi. Quando il nuovo sistema richiede i dati dell'inventario, l'ACL traduce la richiesta in un formato comprensibile dal sistema legacy, recupera i dati e poi li traduce nuovamente in un formato adatto per il nuovo sistema. Questo approccio garantisce che il nuovo sistema rimanga immune dalle complessità del sistema legacy, prevenendo la corruzione dei dati e della logica aziendale, facilitando nel contempo una transizione fluida.

In parole semplici

> Il modello di design Anti-Corruption Layer protegge un sistema dalle complessità e dalle modifiche dei sistemi esterni fornendo un layer di traduzione intermedio.

## Quando Utilizzare il Modello di Anti-Corruption Layer in Java

Utilizza questo modello quando:

* È prevista una migrazione in più fasi, ma è necessario mantenere l'integrazione tra i sistemi nuovi e legacy
* Due o più sottosistemi hanno semantiche diverse, ma devono comunque comunicare
* Quando si integra con sistemi legacy o esterni in cui l'integrazione diretta potrebbe inquinare il modello di dominio del nuovo sistema
* In scenari in cui diversi sottosistemi all'interno di un sistema più grande utilizzano formati di dati o strutture diverse
* Quando c'è la necessità di garantire un accoppiamento debole tra diversi sottosistemi o servizi esterni per facilitare una manutenzione e scalabilità più semplici

## Vantaggi e Svantaggi del Modello di Anti-Corruption Layer

Vantaggi:

* Protegge l'integrità del modello di dominio fornendo un confine chiaro
* Promuove un accoppiamento debole tra i sistemi, rendendo il sistema più resistente alle modifiche dei sistemi esterni
* Facilita un codice più pulito e più manutenibile isolando il codice di integrazione dalla logica aziendale

Svantaggi:

* Introduce complessità aggiuntiva e un potenziale sovraccarico delle prestazioni a causa del processo di traduzione
* Richiede uno sforzo extra nella progettazione e implementazione per garantire che il layer sia efficace senza diventare un collo di bottiglia
* Può portare a una duplicazione dei modelli se non gestito con attenzione

## Applicazioni nel Mondo Reale del Modello di Anti-Corruption Layer in Java

* Architetture a microservizi in cui i singoli servizi devono comunicare senza essere strettamente accoppiati ai propri schemi di dati
* Integrazione di sistemi aziendali, specialmente quando si integra sistemi moderni con sistemi legacy
* Nei contesti delimitati all'interno del Domain-Driven Design (DDD) per mantenere l'integrità di un modello di dominio quando si interagisce con sistemi o sottosistemi esterni

## Pattern di Design Java Correlati

* Adapter: L'Anti-Corruption Layer può essere implementato utilizzando il pattern Adapter per tradurre tra diversi formati di dati o strutture
* Facade: L'Anti-Corruption Layer può essere visto come una forma specializzata del pattern Facade che viene utilizzato per isolare diversi sottosistemi
* Gateway: L'Anti-Corruption Layer può essere utilizzato come un Gateway verso sistemi esterni per fornire un'interfaccia unificata

## Riferimenti e Crediti

* "Domain-Driven Design: Tackling Complexity in the Heart of Software"
* "Implementing Domain-Driven Design"
* "Patterns of Enterprise Application Architecture"
