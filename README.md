# Descripción del Proyecto

Este proyecto tiene como objetivo investigar cómo los transcritos de células humanas tratadas con diferentes probióticos interactúan con proteínas asociadas a enfermedades, virus y bacterias patógenas. Se empleará un enfoque bioinformático que integra datos de expresión génica con bases de datos de interacciones proteína-proteína (PPI) y redes de interacción relacionadas con enfermedades.

## Estructura del Protocolo

El protocolo se divide en varias etapas clave:

### 1. Análisis de Expresión Diferencial (DEA)

- **Objetivo:** Identificar genes diferencialmente expresados en células tratadas con probióticos en comparación con un control.
- **Herramientas:** DESeq2, edgeR, limma.
- **Paso:** Realizar el análisis para identificar genes significativamente regulados.

### 2. Identificación de Proteínas Codificadas por los DEGs

- **Objetivo:** Mapear genes diferencialmente expresados a sus proteínas correspondientes.
- **Herramientas:** UniProt, Ensembl.

### 3. Análisis de Interacciones Proteína-Protéina (PPI)

- **Objetivo:** Identificar interacciones entre proteínas codificadas por los DEGs y proteínas relacionadas con enfermedades.
- **Herramientas:** STRING, BioGRID, IntAct.
- **Paso:** Cargar la lista de proteínas en plataformas PPI.

### 4. Análisis de Enriquecimiento Funcional

- **Objetivo:** Identificar procesos biológicos y funciones moleculares involucradas.
- **Herramientas:** Enrichr, DAVID, GSEA, KEGG.

### 5. Integración con Datos de Patógenos y Enfermedades

- **Objetivo:** Relacionar transcritos tratados con probióticos con proteínas asociadas a enfermedades.
- **Herramientas:** DisGeNET, ViralZone, Virus-Host DB.

### 6. Visualización de Redes

- **Objetivo:** Crear representaciones gráficas de interacciones.
- **Herramientas:** Cytoscape.

### 7. Interpretación Biológica

- **Objetivo:** Extraer conclusiones sobre la influencia de los probióticos en la respuesta celular a patógenos.
