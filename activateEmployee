class EmployeesActionManager extends SubActionManager
{
    public function activateEmployee($req)
    {
        $employee = new Employee();
        $employee->Load("id = ?", array($req->id));

        if (empty($employee->id)) {
            return new IceResponse(IceResponse::ERROR, "Employee Not Found");
        }

        $employee->termination_date = null;
        $employee->status = 'Active';
        $ok = $employee->Save();
        if (!$ok) {
            return new IceResponse(IceResponse::ERROR, "Error occurred while activating employee");
        }

        return new IceResponse(IceResponse::SUCCESS, $employee);
    }
