# **Guion de Pruebas Unitarias**

## **1. Pruebas para `AppointmentHandlerImpl`**

### **Registro de Cita**
#### **Test 1: Registro exitoso de cita**
- **Nombre del Test**: `testRegisterAppointment_Success`
- **Objetivo**: Verificar que una cita se registre correctamente cuando el doctor está disponible.
- **Acciones**: 
  - Simular la existencia del doctor en el repositorio.
  - Verificar que no haya superposición de horarios.
  - Guardar la cita en el repositorio.
- **Resultado esperado**: 
  - La cita se guarda correctamente.
  - Se devuelve el mensaje: `"Appointment confirmed successfully."`

#### **Test 2: Doctor no encontrado**
- **Nombre del Test**: `testRegisterAppointment_DoctorNotFound`
- **Objetivo**: Verificar el comportamiento cuando el doctor no se encuentra.
- **Acciones**:
  - Simular que el doctor no existe en el repositorio.
  - Intentar registrar una cita.
- **Resultado esperado**: 
  - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"Selected doctor does not exist."`

#### **Test 3: Horario no disponible**
- **Nombre del Test**: `testRegisterAppointment_TimeNotAvailable`
- **Objetivo**: Verificar el comportamiento cuando el doctor ya tiene una cita en el horario solicitado.
- **Acciones**:
  - Simular la existencia de una cita en el mismo horario.
  - Intentar registrar una nueva cita.
- **Resultado esperado**: 
  - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"The selected time is not available for this doctor."`

---

### **Consulta del Historial de Citas**
#### **Test 4: Consulta exitosa del historial**
- **Nombre del Test**: `testGetStudentAppointmentHistory_Success`
- **Objetivo**: Verificar la obtención del historial de citas de un estudiante.
- **Acciones**:
  - Simular la existencia de citas en el repositorio.
  - Consultar el historial.
- **Resultado esperado**:
  - Se devuelve una lista con objetos `AppointmentHistoryDTO` correspondientes a las citas del estudiante.

#### **Test 5: Historial vacío**
- **Nombre del Test**: `testGetStudentAppointmentHistory_Empty`
- **Objetivo**: Verificar el comportamiento cuando el historial de citas del estudiante está vacío.
- **Acciones**:
  - Simular que el estudiante no tiene citas en el repositorio.
  - Consultar el historial.
- **Resultado esperado**:
  - Se devuelve una lista vacía.

---

## **2. Pruebas para `DoctorHandlerImpl`**

#### **Test de Registro de Doctor**
- **Test 1**: `registerDoctor_HappyPath`
  - **Objetivo**: Verificar que un doctor se registre correctamente cuando no existe en el sistema.
  - **Acciones**:
    - Simular que el número colegiado del doctor no está registrado.
    - Guardar el doctor en el repositorio.
  - **Resultado esperado**: 
    - El doctor se registra correctamente.
    - Se confirma con el mensaje: `"Doctor registered successfully."`

---

## **3. Pruebas para `ScheduleHandlerImpl`**

#### **Test de Registro de Horario**
- **Test 1**: `testRegisterSchedule_Success`
  - **Objetivo**: Verificar que un horario se registre correctamente para un doctor.
  - **Acciones**:
    - Simular que el doctor existe en el repositorio.
    - Guardar el horario en el repositorio.
  - **Resultado esperado**:
    - El horario se guarda correctamente.
    - Se confirma con el mensaje: `"Schedule registered successfully."`

- **Test 2**: `testRegisterSchedule_DoctorNotFound`
  - **Objetivo**: Verificar el comportamiento cuando el doctor no se encuentra en el sistema.
  - **Acciones**:
    - Simular que el doctor no existe en el repositorio.
    - Intentar registrar un horario para ese doctor.
  - **Resultado esperado**:
    - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"Doctor not found with identification number: 12345"`

#### **Test de Obtención de Horarios por Doctor**
- **Test 3**: `testGetSchedulesByDoctor_Success`
  - **Objetivo**: Verificar que los horarios de un doctor se obtengan correctamente.
  - **Acciones**:
    - Simular la existencia de un doctor y sus horarios en el repositorio.
    - Consultar los horarios por el número de identificación del doctor.
  - **Resultado esperado**:
    - Se devuelve una lista con los horarios del doctor.

- **Test 4**: `testGetSchedulesByDoctor_DoctorNotFound`
  - **Objetivo**: Verificar el comportamiento cuando el doctor no se encuentra en el sistema.
  - **Acciones**:
    - Simular que el doctor no existe en el repositorio.
    - Intentar obtener los horarios del doctor.
  - **Resultado esperado**:
    - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"Doctor not found with identification number: 12345"`

---

## **4. Pruebas para `StudentHandlerImpl`**

#### **Test de Registro de Estudiante**
- **Test 1**: `testRegisterStudent_Success`
  - **Objetivo**: Verificar que un estudiante se registre correctamente cuando no existe en el sistema.
  - **Acciones**:
    - Simular que el ID y el email del estudiante no están registrados.
    - Guardar al estudiante en el repositorio.
  - **Resultado esperado**:
    - El estudiante se registra correctamente.
    - Se confirma con el mensaje: `"Student registered successfully."`

- **Test 2**: `testRegisterStudent_StudentIdAlreadyExists`
  - **Objetivo**: Verificar el comportamiento cuando el ID del estudiante ya está registrado.
  - **Acciones**:
    - Simular que el ID del estudiante ya está registrado.
    - Intentar registrar al estudiante.
  - **Resultado esperado**:
    - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"Student ID is already registered."`

- **Test 3**: `testRegisterStudent_EmailAlreadyExists`
  - **Objetivo**: Verificar el comportamiento cuando el email del estudiante ya está registrado.
  - **Acciones**:
    - Simular que el email del estudiante ya está registrado.
    - Intentar registrar al estudiante.
  - **Resultado esperado**:
    - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"Email is already registered."`

- **Test 4**: `testRegisterStudent_InvalidStudentId`
  - **Objetivo**: Verificar el comportamiento cuando el ID del estudiante es inválido.
  - **Acciones**:
    - Proporcionar un ID inválido.
    - Intentar registrar al estudiante.
  - **Resultado esperado**:
    - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"Student ID must follow the format (e.g., C17640)."`

- **Test 5**: `testRegisterStudent_InvalidEmail`
  - **Objetivo**: Verificar el comportamiento cuando el email del estudiante es inválido.
  - **Acciones**:
    - Proporcionar un email inválido.
    - Intentar registrar al estudiante.
  - **Resultado esperado**:
    - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"Email must be a valid institutional email."`

- **Test 6**: `testRegisterStudent_InvalidPhoneNumber`
  - **Objetivo**: Verificar el comportamiento cuando el número de teléfono del estudiante es inválido.
  - **Acciones**:
    - Proporcionar un número de teléfono inválido.
    - Intentar registrar al estudiante.
  - **Resultado esperado**:
    - Se lanza una excepción `IllegalArgumentException` con el mensaje: `"Phone number must have 8 digits."`

