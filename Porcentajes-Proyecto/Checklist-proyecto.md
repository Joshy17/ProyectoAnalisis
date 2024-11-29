# Documento de Casos de Uso Implementados

Este documento tiene como objetivo detallar los casos de uso implementados en el proyecto **Control de Citas Médicas**, proporcionando un resumen de su estado actual y el porcentaje de avance de cada uno. Este seguimiento permite evaluar el progreso general del desarrollo y garantizar que todas las funcionalidades necesarias se estén cumpliendo según lo planificado.

## Backend:

| **Caso de Uso**              | **Descripción**                                                                                                                                 | **Estado de Implementación (%)** |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| **CU01-RF01: Registrar Estudiante** | Este caso de uso permite registrar un estudiante al sistema proporcionando su información personal y carné universitario para poder hacer uso del sistema de gestión de citas de la clínica universitaria. | 100%                             |
| **CU01-RF07: Registrar Doctor**     | Este caso de uso permite registrar a un doctor en el sistema, proporcionando su información personal y el área especializada, para que pueda brindar servicios de salud. | 100%                             |
| **CU01-RF08: Modificar su horario de trabajo** | Este caso de uso permite al doctor modificar su propio horario de trabajo dentro del sistema, ajustando las franjas horarias disponibles para citas con los estudiantes. | 100%                             |
| **CU01-RF02: Registrar Citas Médicas** | Este caso de uso permite que un estudiante registre una cita médica en el sistema de gestión de citas de la clínica universitaria, seleccionando la especialidad o médico de preferencia y la fecha y hora disponibles, validando la disponibilidad en tiempo real. | 100%                             |
| **CU01-RF06: Consultar la disponibilidad de citas por Especialidad** | Este caso de uso permite que un estudiante consulte la disponibilidad de citas médicas según la especialidad seleccionada. El sistema muestra los doctores disponibles dentro de la especialidad y sus respectivos horarios. | 100%                             |
| **CU01-RF09: Consultar horario de trabajo** | Este caso de uso permite al doctor consultar su horario de trabajo en el sistema de gestión de citas. | 60%                              |
| **CU01-RF11: Modificar cita de su agenda** | Este caso de uso permite que un doctor modifique las citas ya registradas en su agenda dentro del sistema de gestión de citas de la clínica universitaria. | 60%                              |
| **CU01-RF10: Consultar citas asignadas doctor** | Este caso de uso permite que un doctor consulte las citas asignadas en su agenda. | 70%                              |
| **CU01-RF12: Cancelar cita de su agenda** | Este caso de uso permite que un doctor cancele una cita previamente registrada en su agenda dentro del sistema de gestión de citas de la clínica. | 60%                              |
| **CU01-RF03: Cancelar cita estudiante** | Este caso de uso permite que un estudiante cancele una cita previamente registrada en su agenda dentro del sistema de gestión de citas de la clínica universitaria. | 60%                              |
| **CU01-RF05: Consultar historial de citas** | Este caso de uso permite que un estudiante consulte su historial de citas en el sistema de gestión de citas médicas. | 50%                              |

## Frontend:

| **Caso de Uso**              | **Descripción**                                                                                                                                 | **Estado de Implementación (%)** |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| **CU01-RF01: Registrar Estudiante** | Este caso de uso permite registrar un estudiante al sistema proporcionando su información personal y carné universitario para poder hacer uso del sistema de gestión de citas de la clínica universitaria. | 100%                             |
| **CU01-RF07: Registrar Doctor**     | Este caso de uso permite registrar a un doctor en el sistema, proporcionando su información personal y el área especializada, para que pueda brindar servicios de salud. | 100%                             |
| **CU01-RF08: Modificar su horario de trabajo** | Este caso de uso permite al doctor modificar su propio horario de trabajo dentro del sistema, ajustando las franjas horarias disponibles para citas con los estudiantes. | 50%                              |
| **CU01-RF02: Registrar Citas Médicas** | Este caso de uso permite que un estudiante registre una cita médica en el sistema de gestión de citas de la clínica universitaria, seleccionando la especialidad o médico de preferencia y la fecha y hora disponibles, validando la disponibilidad en tiempo real. | 60%                              |
