1. Web application: Log-in

2. Web application: New 'Hoja de Trabajo' + View + Update(Restricted) + Delete(Logical).
3. Web application: List 'Hojas de Trabajo' + Print reports
    - Filter by: 

4. Web application: List 'Workers attendance' + Print reports
    - Each worker's daily report:
        - summary (attendance, #workSessions, #completedJobs, #extraHours #hoursDeficit)
        - Job's details: type, length, status achived, today's status
        - Work Sessions's details: Start time, End time, length, delays.
    - Each worker's monthly report:
    - A group of worker's daily report:
    - A group of worker's monthly report:

5. Mobile application: Log-in
6. Mobile application: Log-out

7. Mobile application: Job's notifications (New, Updated, Cancelled)

8. Mobile application: List Jobs + Map View
    - List Job by day (Past, Today, Future)
9. Mobile application: Job Management (Start, End, Suspend & Report)
    - Use: https://www.typingdna.com

10. Mobile application: List Attendance (Today, This Month, This Year)



Tablas de BD de datos

    users
    - nombre, apellido, direccion, telefono, foto
    - mail, password
    - tipo_contrato (determina sesiones de trabajo)
    - token_celular

    sesiones
    - tipo_session, dia, hr_ini_jornada, hr_fin_jornada, 
    - hr_ini_sesion, hr_fin_sesion,
    - ()
    - min_retraso, min_extra
    - estado (falta/retrasado/ok)
    
    hoja de trabajo
    - dia_reporte, tipo, descripción_trabajo
    - dia_est, hr_est, duracion_est, 
    - id_cliente, id_servicio,
    - persona contacto, telefono

    user_hoja (un trabajador tiene asignadas muchas hojas)
    - id_user, id_hoja

    clientes
    - nombre_cliente, apellido_cliente, direccion, localizacion_gps, telefono

    servicios (brindados)
    - tipo, ini_contrato, fin_contrato. direccion, localizacion_gps