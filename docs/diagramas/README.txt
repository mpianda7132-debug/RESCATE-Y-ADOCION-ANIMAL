@startuml
left to right direction
actor "Ciudadano\n(Reportante)" as Reporter
actor "Rescatista" as Rescuer
actor "Veterinario" as Vet
actor "Voluntario" as Volunteer
actor "Adoptante" as Adopter
actor "Administrador" as Admin
actor "Donante" as Donor

rectangle "Sistema de Control de Rescate y Adopción" {
  Reporter --> (Reportar animal en riesgo)
  Rescuer --> (Registrar rescate)
  Rescuer --> (Asignar transporte)
  Vet --> (Registrar expediente médico)
  Vet --> (Programar cita veterinaria)
  Volunteer --> (Gestionar cuidados diarios)
  Admin --> (Gestionar usuarios y roles)
  Admin --> (Generar reportes)
  Admin --> (Aprobar/Denegar adopciones)
  Adopter --> (Buscar animales)
  Adopter --> (Solicitar adopción)
  Adopter --> (Ver estado de solicitud)
  Donor --> (Realizar donación)
  Donor --> (Solicitar recibo)
  
  (Publicar animal para adopción) .> (Registrar rescate) : include
  (Solicitar adopción) .> (Ver estado de solicitud) : include
  (Realizar donación) .> (Solicitar recibo) : include
  (Registrar expediente médico) .> (Programar cita veterinaria) : include
}
@enduml
